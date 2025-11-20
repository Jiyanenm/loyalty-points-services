
# Loyalty Points Quote Service

A Vert.x-based microservice that calculates loyalty reward points.

## Features
- Calculates base, tier, and promo bonus points
- FX conversion with retry
- Promo service timeout fallback
- Validation + error responses
- Cap at 50,000 points
- Fully covered integration tests with WireMock

## Prerequisites
- Java 17+
- Maven 3.8+

##  Build and Run

1. ### Clone Project

- git clone https://github.com/Jiyanenm/loyalty-points-services

2. ### Build Project

- mvn clean install

3. ###  Run Project
- mvn test
4. ### Run the server
- mvn compile exec:java -Dexec.mainClass="com.example.loyalty.MainVerticle"
  -Default port: 8080

- Example cURL request:

curl -X POST http://localhost:8080/v1/points/quote \

-H "Content-Type: application/json" \
-d '{
"fareAmount": 1234.50,
"currency": "USD",
"cabinClass": "ECONOMY",
"customerTier": "SILVER",
"promoCode": "SUMMER25"
}'
