# TP 13: Web Service SOAP with Spring Boot and Apache CXF

This project implements a SOAP Web Service for managing bank accounts (`Compte`) using Spring Boot and Apache CXF.

## Prerequisites
- Java 17 or higher
- Maven
- SoapUI or Postman (for testing)

## getting Started

### 1. Build the Project
```bash
mvn clean package -DskipTests
```

### 2. Run the Application
```bash
mvn spring-boot:run
```
The application will start on port `8082`.

## Endpoints

| Service | URL | Description |
|---------|-----|-------------|
| **WSDL** | `http://localhost:8082/services/ws?wsdl` | Service Description (WSDL) |
| **H2 Console** | `http://localhost:8082/h2-console` | Database Console |

**H2 Credentials:**
- **URL:** `jdbc:h2:mem:testdb`
- **User:** `sa`
- **Password:** *(empty)*

## Testing

### Using Postman
**URL:** `http://localhost:8082/services/ws`
**Method:** `POST`
**Headers:** `Content-Type: text/xml`

**Body (Create Account):**
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ws="http://ws.demo.example.com/">
   <soapenv:Header/>
   <soapenv:Body>
      <ws:createCompte>
         <solde>1500.0</solde>
         <type>EPARGNE</type>
      </ws:createCompte>
   </soapenv:Body>
</soapenv:Envelope>
```

**Body (Get All Accounts):**
```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ws="http://ws.demo.example.com/">
   <soapenv:Header/>
   <soapenv:Body>
      <ws:getComptes/>
   </soapenv:Body>
</soapenv:Envelope>
```

## Project Structure
- `entities`: JPA Entities and Enums (`Compte`, `TypeCompte`)
- `repositories`: Spring Data JPA Repositories (`CompteRepository`)
- `ws`: SOAP Service Implementation (`CompteSoapService`)
- `config`: CXF Configuration (`CxfConfig`)
"# TP-13-Web-Service-SOAP-avec-JAX-WS-et-Spring-Boot" 
