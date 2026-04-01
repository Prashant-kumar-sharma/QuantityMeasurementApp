# Quantity Measurement App – UC1 (Feet Equality)

### 📌 Overview

- This module checks whether two measurements given in feet are equal.
- It focuses on correct `object equality`, `safe floating-point comparison`, and clean OOP design.

### ⚙️ Use Case: UC1 – Feet Measurement Equality

- Accepts two numerical values in feet  
- Compares them for equality  
- Returns `true` if equal, otherwise `false`

### ⚙️ Key Implementation Points

- Uses a separate `Feet` class to represent a measurement  
- Measurement value is `private` and `final` (immutable)  
- `equals()` is overridden correctly  
- `Double.compare()` is used instead of `==`  
- Handles `null`, type mismatch, and same reference cases safely  

🔗 **Code Link:**  
[UC1: Feet measurement equality](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC1-FeetEquality)

---

# Quantity Measurement App – UC2 (Inches Equality)

### 📌 Overview

- This module checks whether two measurements given in **inches** are equal.
- It extends UC1 by supporting equality checks for inches while following the same design principles.

### ⚙️ Use Case: UC2 – Inches Measurement Equality

- Accepts two numerical values in inches  
- Compares them for equality  
- Returns `true` if equal, otherwise `false`

### ⚙️ Key Implementation Points

- Uses a separate `Inches` class to represent a measurement  
- Measurement value is `private` and `final` (immutable)  
- `equals()` is overridden correctly  
- `Double.compare()` is used instead of `==`  
- Handles `null`, type mismatch, and same reference cases safely  

🔗 **Code Link:**  
[UC2: Feet and Inches measurement equality](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC2-InchEquality)

---

# Quantity Measurement App – UC3 (Generic Quantity Length)

### 📌 Overview

- This module refactors Feet and Inches into a **single generic Length class**.
- It eliminates code duplication by applying the **DRY principle**.
- Supports equality comparison **across different units** (feet ↔ inches).

### ⚙️ Use Case: UC3 – Generic Quantity Length Equality

- Accepts two numerical values along with their respective unit types  
- Converts different units to a **common base unit**  
- Compares values for equality  
- Returns `true` if equivalent, otherwise `false`

### ⚙️ Key Implementation Points

- Uses a **single QuantityLength class**  
- Introduces a `LengthUnit enum` for supported units and conversion factors  
- Eliminates separate Feet and Inches classes  
- Conversion logic is centralised  
- `equals()` supports cross-unit comparison  
- Safe floating-point comparison used  

🔗 **Code Link:**  
[UC3: Generic Quantity Class for DRY Principle](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC3-GenericLength)

---

# Quantity Measurement App – UC4 (Extended Unit Support)

### 📌 Overview

- Extends the generic Length class by adding support for **Yards and Centimeters**.
- Demonstrates scalability without modifying core logic.

### ⚙️ Use Case: UC4 – Extended Quantity Length Equality

- Accepts two numerical values with supported units  
- Supports `feet`, `inches`, `yards`, `centimeters`  
- Converts to common base unit  
- Compares for equality  

### ⚙️ Key Implementation Points

- Extends existing `LengthUnit enum`  
- No change required in core logic  
- Conversion remains centralised  
- Cross-unit equality works seamlessly  

🔗 **Code Link:**  
[UC4: Extended Unit Support](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC4-YardEquality)

---

# Quantity Measurement App – UC5 (Unit-to-Unit Conversion)

### 📌 Overview

- Adds explicit **unit conversion API** to the system.
- Supports conversion across all length units.

### ⚙️ Use Case: UC5 – Unit-to-Unit Conversion

- Accepts value + source unit + target unit  
- Converts via common base unit  
- Returns converted value  

### ⚙️ Key Implementation Points

- Static method:  
  `static double convert(double value, LengthUnit sourceUnit, LengthUnit targetUnit)`
- Validates units and finite values  
- Uses base unit normalisation  
- Maintains floating-point precision tolerance  
- Throws `IllegalArgumentException` for invalid inputs  

🔗 **Code Link:**  
[UC5: Unit-to-Unit Conversion](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC5-UnitConversion)

---

# Quantity Measurement App – UC6 (Addition of Two Length Units)

### 📌 Overview

- Enables addition between two length measurements.
- Supports cross-unit addition and returns result in first operand’s unit.

### ⚙️ Use Case: UC6 – Addition of Two Length Units

- Accepts two numerical values with their respective units  
- Adds them and returns sum in first operand’s unit  

### ⚙️ Key Implementation Points

- Converts operands to common base unit  
- Adds normalised values  
- Converts result back to first operand’s unit  
- Returns new immutable object  
- Validates null and invalid inputs  

🔗 **Code Link:**  
[UC6: Addition of Two Length Units](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC6-UnitAddition)

---

# Quantity Measurement App – UC7 (Addition with Target Unit Specification)

### 📌 Overview

- Extends UC6 by allowing explicit target unit specification.

### ⚙️ Use Case: UC7 – Addition with Target Unit Specification

- Accepts two values + units + target unit  
- Returns result in explicitly specified unit  

### ⚙️ Key Implementation Points

- Overloaded `add()` method  
- Converts → Adds → Converts to target  
- Validates target unit  
- Preserves immutability  

🔗 **Code Link:**  
[UC7: Addition with Target Unit Specification](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC7-TargetUnitAddition)

---

# Quantity Measurement App – UC8 (Standalone LengthUnit Refactoring)

### 📌 Overview

- Refactors `LengthUnit` into standalone top-level class.
- Delegates conversion responsibility fully to `LengthUnit`.

### ⚙️ Use Case: UC8 – Standalone Unit Refactoring

- LengthUnit manages conversion  
- QuantityLength handles equality and arithmetic  
- Backward compatibility maintained  

### ⚙️ Key Implementation Points

- `convertToBaseUnit(double value)`  
- `convertFromBaseUnit(double baseValue)`  
- Clean separation of responsibilities  
- Scalable architecture  

🔗 **Code Link:**  
[UC8: Refactoring Unit Enum to Standalone](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC8-StandaloneUnit)

---

# Quantity Measurement App – UC9 (Weight Equality, Conversion, and Addition)

### 📌 Overview

- Introduces support for weight measurements (`kg`, `g`, `lb`).

### ⚙️ Use Case: UC9 – Weight Measurement

- Equality comparison  
- Unit conversion  
- Addition operations  

### ⚙️ Key Implementation Points

- `WeightUnit enum` (base unit: kilogram)  
- `QuantityWeight class`  
- Cross-unit equality  
- Conversion via base unit  
- Immutable design  

🔗 **Code Link:**  
[UC9: Weight Measurement Equality, Conversion, and Addition (Kilogram, Gram, Pound)](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC9-WeightMeasurement)

---

# Quantity Measurement App – UC10 (Generic Quantity Class with Unit Interface)

### 📌 Overview

- This module refactors the previous category-specific Quantity classes into a single, generic `Quantity<U>` class that works with any measurement category implementing the `IMeasurable` interface.
- It eliminates code duplication, simplifies demonstration methods, and ensures type-safe operations across multiple measurement categories like length and weight.

### ⚙️ Use Case: UC10 – Generic Quantity and Multi-Category Support

- Accepts two numerical values with their respective units
- Supports equality comparison, unit conversion, and addition
- Prevents invalid cross-category comparisons (e.g., length vs. weight)
- Returns a new `Quantity` object for conversion or addition; equality returns a boolean

### ⚙️ Key Implementation Points

- Uses a single generic class: `Quantity<U extends IMeasurable>`
- Holds private final fields: `value` and `unit` (immutable)
- `IMeasurable` interface standardises unit behaviour across categories
- Enums (`LengthUnit`, `WeightUnit`) implement `IMeasurable` and encapsulate conversion logic
- `equals()` compares base unit values using `Double.compare()` and validates unit types
- `convertTo(U targetUnit)` delegates to the unit’s conversion methods and returns new instance
- `add(Quantity<U> other)` and `add(Quantity<U> other, U targetUnit)` perform arithmetic safely
- `hashCode()` and `toString()` overridden for collections and readable output
- Type safety ensured at compile-time via generics; runtime unit class checks prevent cross-category errors
- Demonstration methods in `QuantityMeasurementApp` are generic and unified for all categories

🔗 **Code Link:**  
[UC10: Generic Quantity Class with Unit Interface for Multi-Category Support](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC10-GenericQuantity)

---

# Quantity Measurement App – UC11 (Volume Equality, Conversion, and Addition)

### 📌 Overview

- This module extends the Quantity Measurement Application to support **volume measurements** (litres, millilitres, gallons).
- It demonstrates equality comparison, unit conversion, and addition operations for volume, leveraging the generic `Quantity<U>` class and `IMeasurable` interface. - Volume is treated as a separate category from length and weight, validating the scalability of the generic architecture.

### ⚙️ Use Case:  UC11 – Volume Measurement Equality, Conversion, and Addition

- Accepts numerical values with their respective volume units (LITRE, MILLILITRE, GALLON)
- Compares volumes for equality
- Converts between volume units
- Adds two volume quantities, optionally specifying a target unit

### ⚙️ Key Implementation Points

- `VolumeUnit` enum implements `IMeasurable` with LITRE as the base unit
- Conversion factors: MILLILITRE = 0.001 L, GALLON ≈ 3.78541 L
- Equality uses base unit comparison with epsilon tolerance
- Generic `Quantity<U>` handles conversion and addition without modification
- Maintains type safety: volume cannot be mixed with length or weight
- Objects are immutable; addition and conversion return new instances

🔗 **Code Link:**  
[UC11: Volume Measurement Equality, Conversion, and Addition (Litre, Millilitre, Gallon)](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC11-VolumeEquality)

---

# Quantity Measurement App - UC12 (Subtraction and Division Operations on Quantity Measurements)

### 📌 Overview

- UC12 extends the Quantity Measurement Application by `adding subtraction` and `division operations` to the `generic Quantity<U> model`.
- It builds on `UC1–UC11` and enables full arithmetic manipulation while preserving immutability, type safety, and cross-unit support.

### ⚙️ Use Case: UC12 – Quantity Subtraction & Division

- Subtract two quantities of the same measurement category
- Divide two quantities to obtain a dimensionless ratio
- Support `cross-unit` arithmetic (e.g., feet ↔ inches, litre ↔ millilitre)
- Prevent `cross-category` operations (e.g., length vs weight)

### ⚙️Key Implementation Points

 - Convert operands to base unit before arithmetic
- Validate:
    - Null operands
    - Same measurement category
    - Finite numeric values
    - Division by zero
- Implicit target unit → first operand’s unit
- Explicit target unit supported
- Results rounded to two decimal places (subtraction only)

🔗 **Code Link:**  
[UC12: Subtraction and Division Operations on Quantity Measurements](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC12-SubtractionDivision)

---

# Quantity Measurement App - UC13 (Centralised Arithmetic Logic to Enforce DRY in Quantity Operations)

### 📌 Overview

- UC13 refactors the arithmetic operations introduced in UC12 by centralising all shared validation, unit conversion, and base-unit arithmetic logic into private helper methods.
- This refactoring enforces the DRY (Don’t Repeat Yourself) principle, reduces code duplication, and improves maintainability, while keeping all public APIs and behaviours unchanged.

### ⚙️ Use Case: UC13 Centralised Arithmetic Logic

- Eliminate repeated logic across the add, subtract, and divide methods
- Ensure consistent validation and error handling for all arithmetic operations
- Improve readability and maintainability of arithmetic logic
- Provide a scalable foundation for future operations (multiply, modulo, etc.)
- Preserve all UC12 behaviour and existing test cases

### ⚙️ Key Implementation Points (Brief)

- Centralised validation logic in one private helper method.
- Single helper for base-unit conversion and arithmetic.
- `ArithmeticOperation` enum (ADD, SUBTRACT, DIVIDE) encapsulates operation logic.
- `add`, `subtract`, `divide` delegate to shared helpers.
- Implicit and explicit target unit behaviour preserved.
- Public APIs unchanged; UC12 tests pass as-is.
- DRY enforced, cleaner code, easier future extension.

🔗 **Code Link:**  
[UC13: Centralized Arithmetic Logic to Enforce DRY in Quantity Operations](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC13-ArithematicOperation)


---

# Quantity Measurement App - UC14 (Temperature Measurement with Selective Arithmetic Support)

### 📌 Overview

- UC14 extends the Quantity Measurement Application to support temperature measurements while respecting real-world arithmetic constraints.
- Unlike length, weight, and volume, temperature does not support full arithmetic.
- This use case refactors the IMeasurable interface to make arithmetic optional, enabling temperature units to support only equality and conversion while rejecting unsupported operations with clear errors.

### ⚙️ Use Case: UC14 (Temperature Measurement)

- Introduces **temperature measurement support** with unit conversion and equality
- Restricts **unsupported arithmetic operations** on temperature with clear validation
- Refactors `IMeasurable` to allow **selective operation support** while keeping existing units unchanged

### ⚙️ UC14 – Key Implementation Points

* Introduced `TemperatureUnit` (Celsius, Fahrenheit, Kelvin) with non-linear conversion formulas.
* Refactored `IMeasurable` to add `default methods` for optional arithmetic support.
* Added **SupportsArithmetic** functional interface with lambda-based capability flags.
* Non-temperature units inherit default arithmetic support (**backwards compatible**).
* Temperature explicitly **disables arithmetic** (add, subtract, divide) via overrides.
* `Quantity` validates `operation support upfront` before performing arithmetic.
* Equality and conversion work uniformly via **base-unit normalisation**.
* Cross-category comparisons remain `prohibited and type-safe`.
* Unsupported operations fail fast with **clear UnsupportedOperationException** messages.
* All **UC1–UC13 tests pass unchanged**, ensuring non-breaking evolution.

🔗 **Code Link:**  
[UC14: Temperature Measurement with Selective Arithmetic Support and IMeasurable Refactoring](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC14-TemperatureManagement)

---

# Quantity Measurement App – UC15 (N-Tier Architecture Refactoring)

### 📌 Overview

- This module refactors the application into a **clean N-Tier architecture**.
- It separates responsibilities into **Controller, Service, Repository, and Entity layers**.
- Improves **scalability, maintainability, and testability** while preserving all existing functionality.

### ⚙️ Use Case: UC15 – N-Tier Architecture Implementation

- Introduces layered architecture for better separation of concerns  
- Delegates responsibilities across controller, service, and repository layers  
- Enables independent testing and extension of each layer  
- Maintains backward compatibility with UC1–UC14  

### ⚙️ Key Implementation Points

- **Controller Layer** → Handles input/output and delegates to service  
- **Service Layer** → Contains core business logic (comparison, conversion, arithmetic)  
- **Repository Layer** → Abstracts data persistence (cache-based implementation)  
- **Entity/DTO Layer** → Standardised data transfer and storage objects  
- Uses **Dependency Injection** for loose coupling  
- Implements **Interface Segregation Principle** via service & repository interfaces  
- Introduces `QuantityDTO`, `QuantityModel`, and `QuantityMeasurementEntity`  
- Repository implemented as **Singleton (Cache Repository)**  
- Follows **SOLID principles** and clean architecture design  
- Enables future extensibility (REST APIs, DB integration, etc.)  

🔗 **Code Link:**  
[UC15: N-Tier Architecture Refactoring](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC15-N-Tier)

---

# Quantity Measurement App – UC16 (Database Integration with JDBC)

### 📌 Overview

- This module enhances the application by adding **database persistence using JDBC**.
- Replaces in-memory storage with a **database-backed repository**.
- Enables **audit trails, historical data storage, and scalable persistence**.

### ⚙️ Use Case: UC16 – Database Persistence with JDBC

- Stores quantity measurement operations in a relational database  
- Retrieves historical measurement data  
- Supports switching between cache and database repositories  
- Enables persistent storage across application restarts  

### ⚙️ Key Implementation Points

- Introduces `QuantityMeasurementDatabaseRepository` using **JDBC**  
- Uses **connection pooling** for efficient DB access  
- Implements **parameterized SQL queries** (prevents SQL injection)  
- Adds **transaction management** for consistency  
- Database schema managed via `schema.sql`  
- Configuration handled via `application.properties`  
- Supports **H2 (default), MySQL, PostgreSQL** (configurable)  
- Follows **Maven standard project structure**  
- Adds dependencies: JDBC, H2, SLF4J, Logback, Mockito, JUnit  
- Separates **test and production databases**  
- Maintains backward compatibility with UC15 via interface-based repository  
- Improves scalability, concurrency handling, and query capabilities over cache  

### ⚙️ Key Improvements Over UC15

- Persistent storage (no data loss on restart)  
- Supports concurrent access and transactions  
- Enables SQL-based querying and reporting  
- Better debugging, monitoring, and analytics support  
- Scales beyond memory limitations  

🔗 **Code Link:**  
[UC16: Database Integration with JDBC](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC16-DatabaseIntegration)

---

# Quantity Measurement App – UC17 (Spring Boot REST & JPA Integration)

### 📌 Overview

- This module transforms the application into a **Spring Boot-based RESTful service**.
- It replaces JDBC with **Spring Data JPA** and exposes functionality via **REST APIs**.
- Enhances scalability, maintainability, and enterprise readiness while preserving all existing business logic.

---

### ⚙️ Use Case: UC17 – Spring Boot REST & JPA Integration

- Converts application into a **Spring Boot application**  
- Exposes quantity operations via **REST endpoints (GET, POST, PUT, DELETE)**  
- Replaces JDBC repository with **Spring Data JPA repository**  
- Enables **JSON/XML-based communication**  
- Supports validation, exception handling, and API documentation  

---

### ⚙️ Key Implementation Points

- **Spring Boot Integration**
  - Uses Spring Boot starter parent for auto-configuration  
  - Embedded Tomcat server (no external server required)  

- **REST Controller Layer**
  - Uses `@RestController` to expose APIs  
  - Handles HTTP requests and responses  
  - Supports JSON/XML content negotiation  

- **Service Layer Enhancement**
  - Uses `@Service` annotation  
  - Integrates Spring’s Dependency Injection  
  - Supports `@Transactional` for transaction management  

- **Spring Data JPA**
  - Replaces manual JDBC with `JpaRepository`  
  - Eliminates boilerplate SQL and ResultSet mapping  
  - Supports derived query methods and `@Query`  

- **Entity Refactoring**
  - `QuantityMeasurementEntity` updated with JPA annotations:
    - `@Entity`, `@Table`, `@Id`, `@GeneratedValue`, `@Column`  
  - Uses Lombok to reduce boilerplate (`@Data`, `@NoArgsConstructor`, etc.)  

- **DTO & Validation**
  - `QuantityDTO` enhanced with validation annotations:
    - `@NotNull`, `@NotEmpty`, `@Pattern`, `@AssertTrue`  
  - Introduces `QuantityMeasurementDTO` for API communication  

- **Exception Handling**
  - Global exception handling using `@ControllerAdvice`  
  - Returns proper HTTP status codes and error messages  

- **API Documentation**
  - Integrated Swagger/OpenAPI for interactive API docs  

- **Testing**
  - Uses Spring Boot Test framework  
  - MockMvc for REST endpoint testing  
  - Supports integration and unit testing  

- **Database Support**
  - Default: H2 (in-memory database)  
  - Configurable: MySQL, PostgreSQL  
  - Schema managed via `schema.sql`  

- **Security (Optional Foundation)**
  - Spring Security integration ready  
  - Can support Basic Auth / JWT in future  

- **Monitoring & Actuator**
  - Spring Boot Actuator for health checks and metrics  

---

### ⚙️ Key Improvements Over UC16

- Eliminates JDBC boilerplate code  
- Declarative transaction management  
- Automatic ORM mapping with JPA  
- Built-in REST API support  
- Simplified dependency management  
- Improved testability with Spring Boot Test  
- Better scalability and microservices readiness  
- Integrated monitoring and health checks  

---

### ⚙️ Preconditions

- UC1–UC16 fully working with JDBC persistence  
- Java 11+ installed  
- Maven configured  
- Basic knowledge of Spring Boot, REST, and JPA  
- IDE with Spring support (IntelliJ/Eclipse/VS Code)  
- API testing tool (Postman/curl)  

---

### ⚙️ How to Run

```
# Build the project
mvn clean install

# Run the application
mvn spring-boot:run
```

Application runs on: http://localhost:8080  
H2 Console: http://localhost:8080/h2-console  

---

### ⚙️ Architecture (After UC17)

- **Controller Layer** → REST APIs  
- **Service Layer** → Business logic  
- **Repository Layer** → Spring Data JPA  
- **Model/Entity Layer** → JPA Entities  
- **DTO Layer** → API request/response objects  

---

🔗 **Code Link:**  
[UC17: Spring Boot REST & JPA Integration](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC17-SpringBootRESTJPAIntegration)

---

## 🔐 UC18 – Google Authentication and User Management

## Description
UC18 implements comprehensive **OAuth2 authentication with Google** and advanced **user management** features.  
The system supports both local email/password authentication and Google OAuth2, with seamless user registration and profile management.

## Objective
Provide secure, scalable authentication with Google OAuth2 integration and complete user lifecycle management.

## Key Features
- **Dual Authentication**: Local (email/password) + Google OAuth2
- **Automatic User Registration**: First-time Google users auto-created
- **Profile Management**: User details, profile pictures, email verification
- **Session Management**: JWT tokens with refresh token rotation
- **Security**: Password strength validation, email OTP for password reset
- **Audit Trail**: Track authentication events and user activities

## Authentication Flow

### Local Authentication
1. **Registration**: User provides email, password, name, mobile
2. **Validation**: Strong password requirements enforced
3. **Storage**: Password BCrypt hashed, email marked unverified
4. **Welcome Email**: Sent asynchronously after registration
5. **Login**: Email/password validation, JWT generation
6. **Session**: Access token (10 days) + Refresh token (30 days)

### Google OAuth2 Authentication
1. **Redirect**: User redirected to Google OAuth2 consent screen
2. **Authorization**: Google authenticates user and returns authorization code
3. **Token Exchange**: Backend exchanges code for access/id tokens
4. **User Lookup**: Find existing user by Google provider ID
5. **Auto Registration**: Create new user if not found
6. **JWT Generation**: Generate access and refresh tokens
7. **Frontend Redirect**: Redirect to frontend with JWT

### Password Reset Flow
1. **Request**: User provides email address
2. **Validation**: Check email exists and is verified
3. **OTP Generation**: 6-digit OTP with 15-minute expiry
4. **Email Delivery**: Send OTP to user's email
5. **Verification**: User provides OTP and new password
6. **Update**: Validate OTP, update password, invalidate sessions

## User Management Features

### Profile Management
- **Personal Information**: First name, last name, email, mobile
- **Profile Picture**: URL from OAuth2 provider or custom
- **Email Verification**: Track verification status
- **Authentication Provider**: Track local vs Google authentication
- **Provider ID**: Store OAuth2 provider's unique user ID

### Security Features
- **Password Strength**: 8+ chars, uppercase, lowercase, number, special character
- **Email Validation**: Format validation and domain verification
- **Mobile Validation**: 10-digit number validation
- **Session Security**: JWT with 512-bit signing key
- **Token Rotation**: Refresh tokens rotated on each use
- **Blacklisting**: Access tokens blacklisted on logout

### Audit and Monitoring
- **Authentication Events**: Log successful/failed logins
- **Password Changes**: Track password reset events
- **OAuth2 Events**: Log Google authentication attempts
- **User Activity**: Track measurement operations per user
- **Error Tracking**: Comprehensive error logging

## API Endpoints

### Authentication Endpoints
```http
POST /api/auth/register          # Local user registration
POST /api/auth/login             # Local user login
POST /api/auth/logout            # Secure logout with token blacklisting
POST /api/auth/refresh           # Refresh access token
POST /api/auth/forgotPassword/{email}  # Request password reset OTP
POST /api/auth/resetPassword/{email}   # Reset password with OTP
GET  /oauth2/authorize/google    # Google OAuth2 authorization
GET  /login/oauth2/code/google   # Google OAuth2 callback
```

### User Management Endpoints
```http
GET  /api/user/me               # Get current user profile
PUT  /api/user/profile          # Update user profile
DELETE /api/user/account        # Delete user account
GET  /api/user/history          # Get user's measurement history
GET  /api/user/statistics       # Get user's usage statistics
```

## Security Implementation

### JWT Token Structure
```json
{
  "sub": "123",                    // User ID
  "jti": "uuid",                   // JWT ID for blacklisting
  "iat": 1640995200,              // Issued at
  "exp": 1640998800,              // Expires at
  "roles": ["ROLE_USER"],         // User roles
  "provider": "google",           // Authentication provider
  "email": "user@example.com"     // User email
}
```

### OAuth2 Configuration
```yaml
spring:
  security:
    oauth2:
      client:
        registration:
          google:
            client-id: ${GOOGLE_CLIENT_ID}
            client-secret: ${GOOGLE_CLIENT_SECRET}
            scope: email,profile
        provider:
          google:
            user-name-attribute: sub
```

### Password Security
- **BCrypt Hashing**: 12 rounds for secure password storage
- **Strength Validation**: Comprehensive password policy
- **Reset Token**: 6-digit OTP with 15-minute expiry
- **Email Verification**: Track email verification status

## Integration Points

### Frontend Integration
- **OAuth2 Redirect**: Seamless redirect to Google consent screen
- **Token Storage**: Secure JWT storage in HTTP-only cookies or localStorage
- **Session Management**: Automatic token refresh and logout handling
- **Profile Sync**: Synchronize user profile from Google on login

### Email Service Integration
- **Welcome Emails**: Send welcome email after registration
- **Password Reset**: Send OTP via email for password reset
- **Email Templates**: Professional email templates for all communications
- **Async Processing**: Non-blocking email sending

### Monitoring Integration
- **Actuator Endpoints**: Health checks and metrics
- **Logging**: Structured logging for authentication events
- **Error Tracking**: Comprehensive error handling and logging
- **Performance Monitoring**: Track authentication performance

## Postconditions
- Users can authenticate via email/password or Google OAuth2
- Seamless user registration for first-time Google users
- Secure password reset with email OTP
- Complete audit trail of authentication events
- Scalable user management for enterprise use
- All UC1–UC17 functionality preserved with authenticated access

## Key Concepts
- **OAuth2 Authorization Code Flow** with PKCE
- **JWT-based Stateless Authentication**
- **Refresh Token Rotation** for security
- **Email OTP** for password reset
- **User Profile Management** with OAuth2 integration
- **Security Best Practices** (BCrypt, JWT, HTTPS)
- **Audit Trail** for compliance and monitoring
- **Scalable User Management** for enterprise deployment

🔗 _Code Link:_ 
👉 [UC18 – Google Authentication and User Management](https://github.com/Prashant-kumar-sharma/QuantityMeasurementApp/tree/feature/UC18-SpringSecurityJWTGoogleOAuth2)

---
