# Exploting Authentication Management
**Authtentication** proves an identity with some type of credentials. **Identification** is something that the user uses to **claim** that they are who they say they are. **Authentication is used to prove their identity.**

A web browser may offer visitors a copy of its **digital certificate** as proof of the servers identity.

# Comparing Identification and AAA
**Authentication, authorization, and accounting**.

**Authorization** is **granted** when the users have proven their identity.

**Access control systems** use security controls to ensure that users can only access resources that they are authorized to use, nothing else.

**Accounting** tracks user activity and records it in logs.

Audit logs track activity which allows for the creation of an **audit trail** which allows for recreation of events preceding a security incident.

Authentication must be strong, otherwise authorization and accounting are ineffective.
# Comparing Authentication Factors
**Authentication factors** are the groups of different authentication methods. Some provide stronger assurance than others and the more secure the system is the more likely that the system requires multiple factors for authorization to be granted.

CompTIA recognizes four categories.
1. Something you know (password, pin)
2. Something you have (smart card, phone, usb token)
3. Something you are (fingerprint, biometrics)
4. Somewhere you are (home, office)

Location-based authentication is not typically used by itself.

## Something you know
The lease secure factor because knowledge can be stolen. **NIST SP 800-63B "Digital Identity Guidelines"** list best practices for passwords. 

- hash all passwords
- require multi-factor authentication
- do not require mandatory password resets
- check for common passwords, leak database
- require more than 8 characters
- require users to not use the same password twice on the site
- allow special characters but do not require them

### Password length and complexity
When the number of characters in a password increases, the possibilities of potential passwords increases which means it will be harder to guess. When passwords use different types of characters such as **uppercase letters, lowercase characters, numbers, special characters, etc.** the possibilities increases even more. Also it is good for passwords to not just be simple words.

### Password expiration
This is a setting that sets an interval for a valid password, requiring the user to use a new password when the interval is over. The best practice in current times is to not have password expiration which is based on the premise that users are more likely to use strong passwords if they do not need to keep changing them all the time, when using multi-factor authentication.

### Password history and password reuse
Password history systems remember past passwords and prevents users from re-using them. Common password history systems remember the past 24 use passwords. It has to go through the 24 password cycle before any past password can be used again.


If a user keeps using the same password when they are required to set a new password, it would defeat the purpose of the password expiration policy.

### Password managers
A single store of all passwords. Only need to remember the password to open the vault. The passwords are encrypted so it prevents unauthorized users from seeing them. These can be on a single computer or in the cloud.

## Knowledge based authentication (KBA)
Used to verify the identity of individuals. Help confirm a new user's identity when they are creating an account for the first time. This is called **identity proofing** which is an important step in the **provisioning process** that creates account for new users as they join the organization.

### Static KBA
Typically used to verify identity when you've forgotten your password. These are the questions asked to verify, for example in the Windows 10 installation it asks you three personal security questions.

### Dynamic KBA
Identifies individuals without an account. Queries public and private data sources like credit reports, vehicle registrations, and property records. Crafts multiple-choice questions that only that person would know. The user has a limited amount of time to respond.

## Implementing account lockout policies
User implements the wrong password too many times (three to five times), the system will lock the user's account. The whole purpose of this is to thwart prevent password attacks.

**Account lockout threshold** is the max number of times the user can enter the wrong password.

**Account lockout duration** is the duration of time the user will be locked out when the account lockout threshold is met. If a time is set, then after that time it will unlock. If a time is not set (set to zero) then it will remain locked until an admin unlocks it. 

Many accounts and devices have default passwords. These should be changed before being put out to service or connecting to a network.

### Changing default passwords
Change the name of admin account, default password. Admin accounts do not follow the same lockout policy as regular users (usually) so the password attacks can continue indefinitely.

### Training users about password behaviors
Educate users on the potential damage that can occur. Teach users how to create secure passwords

## Something you have
Something tangible that a user can use to authenticate themselves. Usually in the form of smart cards, security keys, software tokens, and hardware tokens.

### Smart card authentication
Credit card sized card that has an **embedded microchip and certificate**. When inserted into a smart card reader, the smart card reader will read the card's information (them embedded digital certificate) and provide **certificate-based authentication**.

The certificate is a digital file that supports cryptography.  The complex encryption key is better than just a plain old password. The certificate can be used with digital signatures and data encryption. The usage of smart card meets the CIA triad and is **non-repudiation**.

#### Embedded certificate
Holds the user's private key which is matched with a public key when the user logs onto the network. The public key is stored within the system slash network that the smart card readers are connected to.

#### Public key infrastructure (PKI)
Issues and manages certificates. The backend?





`




