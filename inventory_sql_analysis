//View all data to preview
SELECT * FROM TECH_INVENTORY.PUBLIC."Inventory_04";

//Remove 'nan' values, change to null
UPDATE 
    tech_inventory.public."Inventory_04"
set 
    "os_version" = NULL
WHERE 
    "os_version" = 'nan' OR "os_version" = 'NaN';


//Get Total Count of Inventory
SELECT 
    count(*) AS "Total Inventory" 
FROM 
    tech_inventory.public."Inventory_04";

//Get the counts of each model
SELECT 
    "model", COUNT("model")
FROM 
    tech_inventory.public."Inventory_04" 
GROUP BY 
    "model";

//Get the count and percentage for each status
SELECT DISTINCT 
    "status", COUNT("status") AS "Number by status", (COUNT("status") / (SELECT COUNT(*) FROM tech_inventory.public."Inventory_04") *100) AS "Percent by status"
FROM 
    tech_inventory.public."Inventory_04" 
GROUP BY 
    "status";

//Get min, max and avg of os versions
SELECT 
    (SELECT MIN(CAST("os_version" AS INT)) FROM tech_inventory.public."Inventory_04" WHERE "os_version" IS NOT NULL AND "os_version" != 'nan') AS "LOWEST VERSION",
    (SELECT MAX(CAST("os_version" AS INT)) FROM tech_inventory.public."Inventory_04" WHERE "os_version" IS NOT NULL AND "os_version" != 'nan') AS "HIGHEST VERSION", 
    (SELECT AVG(CAST("os_version" AS INT)) FROM tech_inventory.public."Inventory_04" WHERE "os_version" IS NOT NULL AND "os_version" != 'nan') AS "AVERAGE VERSION"
FROM 
    tech_inventory.public."Inventory_04"
WHERE NOT
    "os_version" = 'nan'
LIMIT 1;

//Gets percentage of CBs with no OS version data
SELECT
    ((SELECT COUNT("os_version") FROM tech_inventory.public."Inventory_04" WHERE "os_version" IS NULL OR "os_version" = 'nan') / (SELECT COUNT("os_version") FROM tech_inventory.public."Inventory_04") * 100) AS "Percent of CBs with no os data"
FROM 
    tech_inventory.public."Inventory_04"
LIMIT 1; 

//Retreive Chromebooks which are stolen and lost
SELECT DISTINCT
    "barcode", "model"
FROM 
    tech_inventory.public."Inventory_04"
WHERE
    "status" = 'Lost' OR "status" = 'Stolen';

//Retrieve purchase order data
SELECT
    "date_acquired", count("model") AS "Purchase_Order_Count"
FROM
    tech_inventory.public."Inventory_04"
WHERE
    "date_acquired" IS NOT NULL
GROUP BY
    "date_acquired"
ORDER BY 
    "Purchase_Order_Count" DESC;

