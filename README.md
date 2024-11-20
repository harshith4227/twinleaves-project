create : http://localhost:8080/api/products
Request:
{
    "productName": "Product A",
    "createdOn": "2023-10-01",
    "gtins": [
        {
            "gtin": "G1",
            "batches": [
                {
                    "mrp": 100,
                    "sp": 90,
                    "purchasePrice": 80,
                    "availableQuantity": 100,
                    "inwardedOn": "2023-09-25"
                },
                {
                    "mrp": 100,
                    "sp": 90,
                    "purchasePrice": 80,
                    "availableQuantity": -50,
                    "inwardedOn": "2023-09-30"
                }
            ]
        }
    ]
}

GET apis: to query based on gtins
http://localhost:8080/api/gtins/{gtinId}

To get all the gtins containing batches with positive available quantity
http://localhost:8080/api/gtins/positive-batches

For batches containing negative or zero available quantity, I want just
latest batch (based on inwardedOn filter
http://localhost:8080/api/gtins/latest-negative-batches
