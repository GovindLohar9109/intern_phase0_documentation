## AUTHENTICATION & AUTHORIZATION

[![](https://mermaid.ink/img/pako:eNp1ks1y2jAQx19lR2cSDI4J-NAO4StfkE5I02kNB2EtWBNbSiUZSoBrH6CP2CepLDtpMml9kL27__3telc7EkuGJCTLVG7ihCoDd_2ZAPt0o6mx9hyOjj7AWfRZo4I119xo2ODCvnFeCs-corc7pxq6cSxzYT4eylCvCO0ncg_96BZXXBsLmeDmWVcR-o4wiPKixoanKSwQKGPIgAtgi_lr2lfUexhG13JlYxtuEogVMhSG01RXyoEDDktj6IxRNN3a8hmsUfElR_2PtJErcCHWNOVsD-fRNJEbGCglVQiVG3r_Sbsvky6iEQpU1CBcfrmDO_mAAuowRa25FFXGhWvpctdLMH6AW5liNbDyvHTAYuJ7uLKDY1xhbMBIcFvoU50sJFVs_lreZRkXe7h-o3fOdwnleeWaGJebfUS1lCrTQGNj-9Qh3HO7p57MlUZdsyBW8MbbF88QkS1o_FAxrx1tEpUV3-MsoD5g3NT7mKIdzgtnTAVdofsz_aa_sSPeROUI78u1MZACkMYJKPyeozbw--cv6OYmkYo_2bC9WXbUFWhSIkrjxhmfooEo5kBqZKU4I6FROdZIhiqjhUl2hXpGTIIZzkhoPxkuaZ6aGZmJg017pOKblNlzppL5KiHh0t4Ha-WPzK6-z-lK0b8SFAxVr7jxJPQ9hyDhjvywVtM7Dryg43vtZtBqBM0a2Vqv7x83Ol67c9IKTv3TTnCokSdX0ztuNk68duvED1pBu-UHp83DH5axMK4?type=png)](https://mermaid.live/edit#pako:eNp1ks1y2jAQx19lR2cSDI4J-NAO4StfkE5I02kNB2EtWBNbSiUZSoBrH6CP2CepLDtpMml9kL27__3telc7EkuGJCTLVG7ihCoDd_2ZAPt0o6mx9hyOjj7AWfRZo4I119xo2ODCvnFeCs-corc7pxq6cSxzYT4eylCvCO0ncg_96BZXXBsLmeDmWVcR-o4wiPKixoanKSwQKGPIgAtgi_lr2lfUexhG13JlYxtuEogVMhSG01RXyoEDDktj6IxRNN3a8hmsUfElR_2PtJErcCHWNOVsD-fRNJEbGCglVQiVG3r_Sbsvky6iEQpU1CBcfrmDO_mAAuowRa25FFXGhWvpctdLMH6AW5liNbDyvHTAYuJ7uLKDY1xhbMBIcFvoU50sJFVs_lreZRkXe7h-o3fOdwnleeWaGJebfUS1lCrTQGNj-9Qh3HO7p57MlUZdsyBW8MbbF88QkS1o_FAxrx1tEpUV3-MsoD5g3NT7mKIdzgtnTAVdofsz_aa_sSPeROUI78u1MZACkMYJKPyeozbw--cv6OYmkYo_2bC9WXbUFWhSIkrjxhmfooEo5kBqZKU4I6FROdZIhiqjhUl2hXpGTIIZzkhoPxkuaZ6aGZmJg017pOKblNlzppL5KiHh0t4Ha-WPzK6-z-lK0b8SFAxVr7jxJPQ9hyDhjvywVtM7Dryg43vtZtBqBM0a2Vqv7x83Ol67c9IKTv3TTnCokSdX0ztuNk68duvED1pBu-UHp83DH5axMK4)

## Explanation of the Flow

### Authentication Phase

- When a user visits the platform, they must register or log in.

##### During registration:

- User provides details like name, email, and password.

- Passwords are hashed using bcrypt and stored securely in the database.

- Each user is assigned a role (e.g., user or admin).

##### During login:

- Credentials are validated.

- If valid, the system generates a JWT (JSON Web Token)  token for identity verification.

### Authorization Phase

- Once authenticated, the system checks the user’s role:

- <**User Role**> : Gets access to user features like viewing courses, adding to My Courses, and reading documentation.

- <**Admin Role**>: Redirected to the Admin Dashboard where they can manage courses and users.

- Every subsequent API call or page request uses the JWT token to verify permissions before granting access.

### Security Highlights

<**Password Hashing**> : Protects user credentials.

<**Token-based Authentication**>: Ensures session security without storing sensitive data on the client.

<**Role-based Authorization**>: Prevents unauthorized users from accessing admin functionalities.