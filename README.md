# zero_trust_user_authentication
Zero-Trust Authentication and Access Control Project

This project demonstrates the implementation of a Zero-Trust security model using Python 3. The primary focus is on securing authentication and enforcing role-based access control (RBAC). The project validates user credentials through secure hashing and ensures that only authorized users can access specific resources. This approach aligns with the Zero-Trust principle of “never trust, always verify.”

Project Setup

The project begins by defining a simple user database containing usernames, hashed passwords, and roles. For this demonstration, two users, "Alice" and "Bob," were added:

Alice: Admin role with access to all resources (dashboard, settings, reports).

Bob: User role with limited access (dashboard only).

Password security is implemented using the SHA-256 hashing algorithm to ensure passwords are stored securely and cannot be easily compromised.

Authentication Process

The authentication function verifies user credentials by comparing the hashed password input with the stored hashed password in the database. If the credentials are correct, the function returns the user’s role; otherwise, authentication fails.

Role-Based Access Control

Access control is implemented through an RBAC system. Each role is associated with a specific set of resources that the user can access. The access control logic checks if a user’s role permits access to the requested resource before granting it.

Scenarios Tested

The following scenarios were tested to validate the implementation:

Correct Password for Alice:

Username: Alice

Password: password123

Resource: settings

Outcome: Authentication succeeded, and Alice was granted access to the settings resource due to her admin role.

Wrong Password for Alice:

Username: Alice

Password: wrongpassword

Resource: settings

Outcome: Authentication failed for Alice as the password did not match the hashed value.

Bob Attempts to Access Settings:

Username: Bob

Password: mypassword

Resource: settings

Outcome: Authentication succeeded, but Bob was denied access to the settings resource because his role (user) does not include access to settings.

Invalid User (Charlie):

Username: Charlie

Password: somepassword

Resource: dashboard

Outcome: Authentication failed for Charlie as the username does not exist in the database.

Execution Environment

The project was developed and tested in a Jupyter Lab environment running Python 3. It was thoroughly tested for various scenarios to ensure robustness and saved as part of a GitHub repository for future reference and collaboration.

Conclusion

This project successfully showcases the principles of Zero-Trust security by integrating secure authentication and role-based access control. It highlights the importance of verifying every request, ensuring that only authenticated users with the proper roles can access resources. This implementation can serve as a foundation for more advanced Zero-Trust models in real-world applications.
