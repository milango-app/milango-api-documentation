
# Milango API Integration Documentation

**Revision:** 2.0  
**Format:** RESTful JSON APIs  
**Authentication:** Token-based  
**Environment:** Separate testing/staging environment must be provided  
**Performance:** Optimized for expected user load  

---

## General Guidelines

- All APIs should be fully documented (Swagger or Postman collections recommended).
- JSON format is required for requests and responses.
- Token-based authentication must be enforced.
- Testing environment and data are required for the beta phase.
- RESTful API conventions are recommended.

---

## Endpoints

### 1. Users

**Get User**

Retrieve user information by phone number.  
*Used for login and identity validation.*

- **Params:**
  - `phone`: user phone number as the phone number is the unuiq iddenfier on the app
- **Response example:**
  ```json
  {
    "user_id": "...", // (Required)
    "first_name": "Name",
    "last_name": "Name",
    "gender": "MALE", // support three values 1. empty "", 2. "MALE", and 3. "FEMALE".
    "email": "valid@email.com",
    "birth_date": "1993-01-01",
    "units": [ // (Required)
      {
        "unit_id": "eg8910", // (Required)
        "unit_name": "Unit A 50", // (Required)
        "unit_code": "unit-11", // (Required)
        "unit_role":  "OWNER", // optional if the CRM/ERP has the owners only.
        "project_id": "e6f11...", // (Required)
        "project_name": "Project 1",
        "status": "MOVED_IN" // (Required)
      }
    ]
  }


