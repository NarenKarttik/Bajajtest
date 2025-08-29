# Bajaj Test Spring Boot Application

## Overview
This Spring Boot application demonstrates how to:
- Send a POST request to generate a webhook and access token on startup
- Use the received webhook URL and access token to send a SQL query as a POST request

## How it Works
1. **On Startup:**
   - The application sends a POST request to `https://bfhldevapigw.healthrx.co.in/hiring/generateWebhook/JAVA` with your name, registration number, and email.
   - It receives a webhook URL and an access token in the response.
2. **Webhook POST:**
   - The application sends a second POST request to the received webhook URL.
   - The request includes the access token in the `Authorization` header and a SQL query in the JSON body.
   - The response from the webhook is printed to the console.

## Main Files
- `src/main/java/com/example/demo/BajajTestApplication.java`: Main Spring Boot entry point.
- `src/main/java/com/example/demo/StartupWebhookRunner.java`: Contains the startup logic for POST requests.

## How to Run
1. **Build the project:**
   ```sh
   ./mvnw clean package
   ```
2. **Run the application:**
   ```sh
   ./mvnw spring-boot:run
   ```
3. **Output:**
   - The console will display the webhook URL, access token, and the webhook POST response.

## Dependencies
- Spring Boot Starter
- Spring Boot Starter Web (for RestTemplate)
- Jackson Databind (for JSON parsing)

## Customization
- To change the SQL query, edit the `sqlQuery` variable in `StartupWebhookRunner.java`.

## Example Output
```
Webhook URL: https://bfhldevapigw.healthrx.co.in/hiring/testWebhook/JAVA
Access Token: <your-access-token>
Webhook POST response: {"success":true,"message":"Webhook processed successfully"}
```

---

**Author:** Naren Karttik
