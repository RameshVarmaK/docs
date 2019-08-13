---
title: "Login Configuration"
id: "login-configuration"
---

**Configuration** defines the login behavior once authentication is enabled.

There are two behaviors that can be defined:

- page and
- page.

You can also configure the session timeout behavior.

# Login Page

1. the Login should be handled: using a **page** - you can use the default login page provided by Studio or create your own page; [![](../assets/security_loginpage_1.png)](../assets/security_loginpage_1.png)
2. using a **dialog** pop-up provided by Studio. This dialog is present in the _page_ as "" and can be customized. [![](../assets/security_logindialog.png)](../assets/security_logindialog.png)

# Landing Page

1. the user should land: **page** can be defined to be different for different roles the user is assigned. For example, an admin might want to start with the employee management page, while a user would start with their profile page. In such cases, the employee management page would be the Landing Page for the admin role and the employee profile page would be the Landing Page for the user role.
2. things that you need to be aware of regarding the landing page configured here and the home page configured in the [**Settings**](http://[supsystic-show-popup id=108]) dialog ( [accessed from the Project Configurations of Workspace](http://[supsystic-show-popup id=107])):
    - case the app is not secure, user is redirected to the Home page configured in the project settings
    - case the app is secure but the Home Page is not (permission set to everyone), user is redirected to the Home page configured in the project settings
    - case the app and Home Page are secure (permission set to specific user role), user is redirected to the configured login page as per the user role [![](../assets/security_landingpage.png)](../assets/security_landingpage.png)

# Timeout

1. **timeout behavior** can also be defined. Session timeout occurs due to session inactivity or deletion of browser cookies. The re-login mechanism in the app can be configured as follows:
    
    - - : On session timeout, the user is redirected to the configured login page. Any page can be configured to redirect the user on session timeout.
        - : On session timeout, a dialog pops-up, for re-logging in the app.
    
    [![](../assets/security_reloginpage.png)](../assets/security_reloginpage.png)
    
    In both the cases, on re-login, redirection occurs based upon the user login:
    
    - user (last logged-in), the user is redirected to the last page(session timeout through Page) or remains in the same state(session timeout through Dialog).
    - user, the user is redirected to the Landing Page against the user role
    
    Control comes to the _callback_ function as soon as session timeout is detected by the app. You can perform a custom action like clearing sensitive data, etc in this callback. This function can be invoked from file:
    
     = function () {
    
    };
    
    This function can be invoked from any file:
    
     = function () {
    
    };
    

# session timeout

By default, the session timeout is set to 30 minutes. You can choose to change it [![](../assets/security_timeout.png)](../assets/security_timeout.png)

< Role Based Access

Variables >

7\. Security

- 7.1 App Security Overview
    - [Overview](/learn/app-security/app-security/#)
    - [How Security Works](/learn/app-security/app-security/#working)
    - [How Security is Implemented](/learn/app-security/app-security/#implementation)
    - [Security Terminology](/learn/app-security/app-security/#terminology)
- 7.2 Authentication
    - [Overview](/learn/app-security/authentication/)
    - [Security Providers](/learn/app-security/authentication/#security-providers)
        - [Demo](/learn/app-security/authentication/#demo)
        - [Database](/learn/app-security/authentication/#database)
        - [LDAP](/learn/app-security/authentication/#ldap)
        - [Active Directory](/learn/app-security/authentication/#ad)
        - [CAS](/learn/app-security/authentication/#cas)
        - [SAML](/learn/app-security/authentication/#saml)
        - [Custom](/learn/app-security/authentication/#custom)
- 7.3 Authorization
    - [Overview](/learn/app-security/authorization/)
    - [User Onboarding](/learn/app-security/authorization/#user-onboarding)
    - [App Roles](/learn/app-security/authorization/#app-roles)
- 7.4 Access Levels & Permissions
    - [Overview](/learn/app-security/access-levels-permissions/)
    - [Setting Permissions](/learn/app-security/access-levels-permissions/#setting-permissions)
    - [Role Based Access to Widgets](/learn/app-security/access-levels-permissions/#role-based-access)
- [7.5 Login Configuration](#)
    - [Overview](#)
    - [Login Page](#login-page)
    - [Landing Page](#landing-page)
    - [Session Timeout](#session-timeout)
- 7.6 Security Related Variables
    - [Overview](/learn/app-security/security-variables)
- 7.7 SSL Encryption
    - [Overview](/learn/app-security/ssl-encryption/)
- 7.8 OWASP
    - [Overview](/learn/app-security/owasp/)
    - [Preventing XSS Attacks](/learn/app-security/owasp/#xss)
    - [Preventing CSRF Attacks](/learn/app-security/owasp/#csrf)
- 7.9 Single Sign-On (CAS)
    - [Overview](/learn/app-security/central-authentication-system/)
- 7.10 Token Based Authentication
    - [Overview](/learn/app-security/token-based-authentication/)
    - [How Token Based Authentication Works](/learn/app-security/token-based-authentication/#working)
    - [What is Token](/learn/app-security/token-based-authentication/#token)
    - [Token Repository](/learn/app-security/token-based-authentication/#token-repository)
    - [Token Request](/learn/app-security/token-based-authentication/#token-request)
    - [API Invocation](/learn/app-security/token-based-authentication/#api-invocation)
    - [Token Validity](/learn/app-security/token-based-authentication/#token-validity)
- 7.11 SAML Integration
    - [Overview](/learn/app-development/app-security/saml-integration/)
    - [Profiles](/learn/app-development/app-security/saml-integration/#profiles)
    - [Integration](/learn/app-development/app-security/saml-integration/#integration)
    - [Configuration Files](/learn/app-development/app-security/saml-integration/#files)
    - [Deployment](/learn/app-development/app-security/saml-integration/#deployment)
    - [Troubleshooting](/learn/app-development/app-security/saml-integration/#troubleshooting)
    - [Use Cases](/learn/app-development/app-security/saml-integration/#use-cases)