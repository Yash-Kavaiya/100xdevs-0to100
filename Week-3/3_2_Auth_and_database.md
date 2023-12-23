# Authentication

1 . Hashing
2. Encryption
3. Json web tokens
4. Local storage

| Aspect        | Hashing                                       | Encryption                                      |
|---------------|-----------------------------------------------|-------------------------------------------------|
| Purpose       | Converts data into a fixed-size string of text (hash) | Converts data into a ciphertext for security |
| Reversibility | Non-reversible (one-way function)               | Reversible (can be decrypted back to original)  |
| Output        | Fixed length output (hash)                      | Variable length output (ciphertext)            |
| Key Usage     | No key required                                | Requires a key for encryption/decryption       |
| Use Case      | Password storage, integrity verification        | Secure data transmission, confidentiality      |
| Security      | One-way transformation, less susceptible to decryption | Vulnerable to decryption if the key is compromised |
| Collision     | Possible (two different inputs generate the same hash) | Should not occur (due to unique keys)        |

Explanation:

1. **Purpose:**
   - **Hashing:** It's used to generate a fixed-size string of text (hash) from input data. It's commonly used for password storage and ensuring data integrity.
   - **Encryption:** It transforms data into ciphertext to ensure confidentiality during transmission or storage.

2. **Reversibility:**
   - **Hashing:** It's non-reversible. Once data is hashed, it cannot be reversed back to the original input.
   - **Encryption:** It's reversible. Encrypted data can be decrypted back to its original form using a key.

3. **Output:**
   - **Hashing:** Produces a fixed length output (hash) regardless of the input size.
   - **Encryption:** Produces variable length output (ciphertext) depending on the input size and algorithm used.

4. **Key Usage:**
   - **Hashing:** Doesn’t require a key.
   - **Encryption:** Requires a key for both encryption and decryption.

5. **Use Case:**
   - **Hashing:** Commonly used for password hashing, data integrity checks.
   - **Encryption:** Used for secure communication, ensuring confidentiality.

6. **Security:**
   - **Hashing:** Provides one-way transformation. It's less susceptible to decryption attacks.
   - **Encryption:** Vulnerable to decryption if the key is compromised.

7. **Collision:**
   - **Hashing:** Collisions are possible (two different inputs generating the same hash), although modern hash functions aim to minimize this.
   - **Encryption:** Should not occur if using strong encryption algorithms and unique keys.

Remember, the choice between hashing and encryption depends on the specific security needs of the system/application. Hashing is preferred for storing passwords securely, while encryption is used for secure data transmission or confidentiality.

JSON Web Tokens (JWTs) are a compact and self-contained way to transmit information between parties as a JSON object. They are used for authentication and information exchange, commonly in web applications. JWTs are composed of three parts separated by dots: the header, the payload, and the signature. Each part is Base64 encoded but not encrypted.

1. **Header:** Contains metadata about the type of token and the algorithm used for its creation. Typical headers include:
   - `alg`: The cryptographic algorithm used to secure the token (e.g., HMAC SHA256, RSA).
   - `typ`: Specifies the token type, which is typically JWT.

2. **Payload:** Contains the claims. Claims are statements about an entity (user) and additional data. There are three types of claims:
   - **Reserved Claims:** These are predefined claims by the JWT standard (e.g., `iss` for the issuer, `exp` for expiration time, `sub` for subject, etc.).
   - **Public Claims:** These are custom claims created by those using JWTs, often for application-specific information.
   - **Private Claims:** These are custom claims that are agreed upon between parties and are not meant to be used by others.

3. **Signature:** It's created by taking the encoded header, encoded payload, a secret key (in case of HMAC algorithm), and then applying the algorithm specified in the header. This signature is used to verify that the sender of the JWT is who it says it is and to ensure that the message wasn’t tampered with.

JWTs are commonly used for:

- **Authentication:** Once a user is logged in, each subsequent request includes the JWT, allowing the user to access routes, services, and resources.
- **Information Exchange:** They are used as a means of transferring data securely between parties, often as a token of authorization or access control.

Advantages of JWTs include their compactness, ease of transmission over HTTP headers or URLs, and their statelessness, which means the server does not need to maintain a session state. However, they should be used with caution: improper implementation or storage of JWTs, especially without proper encryption of sensitive information, can lead to security vulnerabilities.
