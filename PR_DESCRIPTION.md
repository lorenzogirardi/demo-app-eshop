# Demo Mode Implementation

## Overview
This PR configures the e-commerce application to run in demo mode with no authentication requirements and sample images from the internet. It's designed to make the application easy to run locally for demonstration purposes without needing external services like Auth0 or MongoDB.

## Changes Made

### 1. Authentication Bypass
- Modified `src/lib/authOptions.ts` to use a mock user session instead of Auth0
- Updated `src/app/Navbar/UserMenuButton.tsx` to display a demo user with an avatar from the internet

### 2. Mock Database Implementation
- Created `src/lib/db/mock-db.ts` with sample product data
- Modified `src/lib/db/prisma.ts` to use the mock database instead of real Prisma client
- Products now have images sourced from public URLs

### 3. Local Cart Functionality
- Modified `src/lib/db/cart.ts` to use cookies for local cart ID
- Simplified cart operations to work without authentication

### 4. Configuration Updates
- Updated `package.json` to use port 12000 and allow external connections
- Added comprehensive documentation in README.md

### 5. Documentation
- Updated README.md with detailed instructions on running the demo
- Added section on how AI can boost productivity with modern web apps

## How to Test
1. Clone the repository
2. Run `npm install`
3. Run `npm run dev`
4. Access the application at http://localhost:12000
5. Verify you can browse products, add items to cart, and proceed to checkout without authentication

## Notes for Level 1 Support
- This demo version doesn't require any external services or databases
- All product data is mocked and stored in memory
- User authentication is bypassed with a mock user
- The application should work out of the box with just npm install and npm run dev
- If there are any issues, check the console logs for errors

## Future Improvements
- Add more sample products with diverse images
- Implement a mock checkout process
- Add more detailed product information