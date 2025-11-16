# FRD — Online Payment Processing Module

## 1. Overview
New payment module supporting credit cards, Apple Pay, Google Pay.

## 2. System Features
### Feature: Payment Authorization
- Accepts card number, expiry, CVV
- Sends to payment gateway
- Receives approval or decline

### Feature: Receipt Generation
- Email receipt sent automatically

## 3. Functional Requirements
FR-001: System must validate credit card number format  
FR-002: If payment = success, then generate receipt  
FR-003: If payment = decline, show message  
FR-004: System must store transaction ID in DB  

## 4. Data Schema
**Table: payment_transactions**  
- id  
- order_id  
- amount  
- status  
- created_at  

## 5. Error Handling
- Timeout → retry up to 3 times  
- Declined → show gateway message  

## 6. APIs
POST /api/payment/authorize  
POST /api/payment/refund  
