# Project Overview
This document showcases a UML-compliant use case diagram detailing how various users interact with all essential features of the Airbnb Clone backend system, as defined by the project's requirements

# Actors Overview
The system identifies five primary actors that interact with the Airbnb Clone backend:

1. Guest (Primary Actor)
Role : End users who search for and book properties
Capabilities : Registration, property search, booking management, payments, reviews
Access Level : Standard user permissions
2. Host (Primary Actor)
Role : Property owners who list and manage rental properties
Capabilities : Property management, booking approval, calendar management, host payouts
Access Level : Enhanced permissions for property management
3. Admin (Primary Actor)
Role : System administrators who manage the platform
Capabilities : User management, content moderation, analytics, system monitoring
Access Level : Full administrative permissions
4. Payment Gateway (External Actor)
Role : Third-party payment processing service (Stripe/PayPal)
Capabilities : Process payments, handle refunds, manage transactions
Integration : RESTful API integration
5. Email Service (External Actor)
Role : External email service provider (SendGrid/Mailgun)
Capabilities : Send notifications, verification emails, system alerts
Integration : SMTP/API integration
Use Case Systems
The use case diagram is organized into seven major functional systems:

1. User Management System
Handles user lifecycle and authentication processes:

UseCase1 : Register Account - Multi-role registration with email verification
UseCase2 : Login/Logout - JWT-based authentication with session management
UseCase3 : Manage Profile - Profile information and preferences management
UseCase4 : Verify Email - Email verification workflow for account activation
UseCase5 : Reset Password - Secure password reset functionality
UseCase6 : Enable 2FA - Two-factor authentication setup
UseCase7 : OAuth Login - Social media authentication (Google, Facebook, GitHub)
2. Property Management System
Enables hosts to create and manage property listings:

UseCase8 : Create Listing - Comprehensive property creation with details
UseCase9 : Edit Listing - Modify existing property information
UseCase10 : Upload Photos - Image management with cloud storage integration
UseCase11 : Manage Availability - Calendar management and availability updates
UseCase12 : Set Pricing - Dynamic pricing configuration with seasonal rates
UseCase13 : Delete/Archive Listing - Soft delete functionality for listings
UseCase14 : Manage House Rules - Property-specific rules and policies
3. Search & Discovery System
Facilitates property discovery for guests:

UseCase15 : Search Properties - Location-based and keyword search
UseCase16 : Filter Results - Advanced filtering by price, amenities, capacity
UseCase17 : View Property Details - Detailed property information display
UseCase18 : Save Favorites - Wishlist functionality for properties
UseCase19 : Browse by Location - Geographic browsing capabilities
UseCase20 : View on Map - Interactive map integration with property markers
4. Booking Management System
Manages the complete booking lifecycle:

UseCase21 : Make Booking Request - Guest-initiated booking process
UseCase22 : Approve/Reject Booking - Host booking approval workflow
UseCase23 : Modify Booking - Date changes and booking modifications
UseCase24 : Cancel Booking - Cancellation process with policy enforcement
UseCase25 : Check Availability - Real-time availability validation
UseCase26 : Manage Calendar - Host calendar management and blocking
UseCase27 : Check-in/Check-out - Booking completion process
5. Payment Processing System
Handles all financial transactions:

UseCase28 : Process Payment - Secure payment processing with multiple gateways
UseCase29 : Handle Refunds - Automated refund processing based on policies
UseCase30 : Manage Security Deposit - Security deposit handling and release
UseCase31 : Generate Invoices - Automated invoice generation for bookings
UseCase32 : Process Host Payouts - Scheduled host payment processing
UseCase33 : Calculate Taxes - Tax calculation and collection
6. Reviews & Ratings System
Manages feedback and trust-building:

UseCase34 : Write Review - Post-stay review submission
UseCase35 : Rate Property/Host - Multi-category rating system
UseCase36 : Respond to Reviews - Host response to guest reviews
UseCase37 : View Reviews - Review display and filtering
UseCase38 : Report Review - Review reporting for inappropriate content
UseCase39 : Moderate Reviews - Admin review moderation and approval
7. Communication System
Enables secure user communication:

UseCase40 : Send Messages - Real-time messaging between users
UseCase41 : Receive Notifications - Multi-channel notification delivery
UseCase42 : Manage Notification Preferences - User notification settings
UseCase43 : Share Files in Chat - File and image sharing in messages
8. Administrative System
Provides comprehensive system management:

UseCase44 : Manage Users - User account administration
UseCase45 : Moderate Content - Content approval and moderation
UseCase46 : View Analytics - Platform usage and performance analytics
UseCase47 : Generate Reports - Business intelligence and reporting
UseCase48 : Suspend Accounts - Account suspension and management
UseCase49 : Approve Listings - Listing approval workflow
UseCase50 : Monitor System Health - System monitoring and maintenance

Actor-System Interactions
Guest Interactions (21 Use Cases)
Guests interact with core platform features including user management, search, booking, payment, and communication systems. They have read-only access to property information and can initiate booking requests.

Host Interactions (20 Use Cases)
Hosts have enhanced capabilities including property management, booking approval, calendar management, and payout processing. They can respond to reviews and manage guest communications.

Admin Interactions (8 Use Cases)
Admins focus on system administration, content moderation, user management, and analytics. They have full access to all system data and administrative functions.

External System Interactions
Payment Gateway : Integrates with 6 payment-related use cases
Email Service : Supports 3 notification and verification use cases
Key Relationships
The diagram includes several important UML relationships:

Include Relationships
UseCase21 includes UseCase25 : Booking requests must check availability
UseCase28 includes UseCase33 : Payment processing includes tax calculations
UseCase24 includes UseCase29 : Cancellations include refund processing
UseCase34 includes UseCase35 : Writing reviews includes rating submission
UseCase8 includes UseCase10 : Creating listings includes photo uploads
Extend Relationships
UseCase22 extends UseCase41 : Booking approvals trigger notifications
UseCase21 extends UseCase41 : Booking requests trigger notifications
UseCase24 extends UseCase41 : Cancellations trigger notifications
Business Rules
Authentication & Authorization
All users must register and verify their email before accessing full features
Role-based access control ensures proper permission management
JWT tokens expire after configured intervals for security
Booking Business Rules
Guests cannot book unavailable dates
Hosts must approve booking requests within 24 hours
Cancellation policies determine refund amounts
Double bookings are prevented through database constraints
Payment Processing Rules
Payments are processed upfront for confirmed bookings
Host payouts occur 24 hours after guest check-in
Security deposits are released 48 hours after check-out
Refunds follow the property's cancellation policy
Review System Rules
Reviews can only be submitted after completed stays
Both guests and hosts can review each other
Reviews are publicly visible after submission
Inappropriate reviews can be reported and moderated