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
