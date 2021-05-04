#KMeans
CREATE OR REPLACE MODEL 
`coral-lightning-299616.hellosupermarket.segment`
OPTIONS(model_type='kmeans',num_clusters=4, kmeans_init_method='kmeans++',max_iterations=50)
AS(
    SELECT 
    COUNT(DISTINCT BASKET_ID)/COUNT(DISTINCT SHOP_WEEK) AS AVG_WEEKLY_VISIT,
    SUM(SPEND)/COUNT(DISTINCT BASKET_ID) AS TICKET_SIZE,
    FROM `coral-lightning-299616.hellosupermarket.kayepatt`
    WHERE CUST_CODE IS NOT NULL 
    GROUP BY CUST_CODE
)

#CentroidID

SELECT 
* EXCEPT(nearest_centroids_distance)
FROM 
ML.PREDICT(MODEL `coral-lightning-299616.hellosupermarket.segment`,
(
    SELECT 
    DISTINCT CUST_CODE,
    COUNT(DISTINCT BASKET_ID)/COUNT(DISTINCT SHOP_WEEK) AS AVG_WEEKLY_VISIT,
    SUM(SPEND)/COUNT(DISTINCT BASKET_ID) AS TICKET_SIZE,
    FROM `coral-lightning-299616.hellosupermarket.kayepatt`
    WHERE CUST_CODE IS NOT NULL 
    GROUP BY CUST_CODE
))
