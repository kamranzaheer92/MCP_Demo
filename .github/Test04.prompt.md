# Sauce Demo Critical Test Cases

## 1. Authentication Test Cases

### TC-AUTH-001: Standard User Login
**Priority:** High  
**Description:** Verify successful login with standard user  
**Precondition:** User is on login page  
**Test Steps:**
1. Enter username "standard_user"
2. Enter password "secret_sauce"
3. Click LOGIN button
**Expected Results:**
- User successfully logs in
- User is redirected to inventory page
- Product list is visible

### TC-AUTH-002: Locked Out User
**Priority:** High  
**Description:** Verify locked out user cannot access system  
**Test Steps:**
1. Enter username "locked_out_user"
2. Enter password "secret_sauce"
3. Click LOGIN button
**Expected Results:**
- User cannot log in
- Error message displayed
- User remains on login page

### TC-AUTH-003: Performance Glitch User
**Priority:** Medium  
**Description:** Verify system behavior with performance_glitch_user  
**Test Steps:**
1. Enter username "performance_glitch_user"
2. Enter password "secret_sauce"
3. Click LOGIN button
4. Monitor response time
**Expected Results:**
- User logs in successfully but with noticeable delay
- Loading indicator shown during delay
- Eventually redirects to inventory page

## 2. Product Catalog Test Cases

### TC-PROD-001: Product Sorting
**Priority:** High  
**Description:** Verify product sorting functionality  
**Test Steps:**
1. Log in as standard user
2. Navigate to inventory page
3. Test each sorting option:
   - Name (A to Z)
   - Name (Z to A)
   - Price (low to high)
   - Price (high to low)
**Expected Results:**
- Products sort correctly for each option
- Sort persists when navigating
- Sort dropdown shows correct selection

### TC-PROD-002: Product Details
**Priority:** Medium  
**Description:** Verify product detail page functionality  
**Test Steps:**
1. Click on any product name/image
2. Verify product details page
3. Click Back button
**Expected Results:**
- Correct product details displayed
- Image loads properly
- Price matches inventory page
- Back button returns to inventory

## 3. Shopping Cart Test Cases

### TC-CART-001: Add to Cart
**Priority:** High  
**Description:** Verify adding items to cart  
**Test Steps:**
1. Click ADD TO CART for multiple items
2. Verify cart badge count
3. Click cart icon
**Expected Results:**
- Items added successfully
- Cart badge updates correctly
- Cart page shows correct items
- Prices are accurate

### TC-CART-002: Remove from Cart
**Priority:** High  
**Description:** Verify removing items from cart  
**Test Steps:**
1. Add items to cart
2. Remove items using:
   - REMOVE button on inventory page
   - REMOVE button in cart
**Expected Results:**
- Items removed successfully
- Cart badge updates
- Cart total updates
- REMOVE button changes to ADD TO CART

### TC-CART-003: Cart Persistence
**Priority:** Medium  
**Description:** Verify cart state persistence  
**Test Steps:**
1. Add items to cart
2. Navigate through different pages
3. Log out and log back in
**Expected Results:**
- Cart items persist during navigation
- Cart resets after logout

## 4. Checkout Process Test Cases

### TC-CHECK-001: Checkout Information
**Priority:** High  
**Description:** Verify checkout information form  
**Test Steps:**
1. Add items to cart
2. Click CHECKOUT
3. Enter personal information:
   - First Name
   - Last Name
   - ZIP/Postal Code
4. Click CONTINUE
**Expected Results:**
- Form accepts valid input
- Validation works for empty fields
- Proceeds to checkout overview

### TC-CHECK-002: Checkout Overview
**Priority:** High  
**Description:** Verify checkout overview page  
**Test Steps:**
1. Complete checkout information
2. Review checkout overview
3. Verify:
   - Item list
   - Item totals
   - Tax calculation
   - Total calculation
4. Click FINISH
**Expected Results:**
- All items listed correctly
- Prices calculated correctly
- Tax calculated accurately
- Total sum is correct

### TC-CHECK-003: Order Completion
**Priority:** High  
**Description:** Verify order completion process  
**Test Steps:**
1. Complete checkout overview
2. Click FINISH
3. Verify confirmation page
**Expected Results:**
- Order confirmation displayed
- Thank you message shown
- Cart is emptied
- Can return to products

## 5. Navigation Test Cases

### TC-NAV-001: Menu Navigation
**Priority:** Medium  
**Description:** Verify menu functionality  
**Test Steps:**
1. Click menu button
2. Test each menu item:
   - All Items
   - About
   - Logout
   - Reset App State
**Expected Results:**
- Menu opens/closes correctly
- Each link works properly
- Reset App State clears cart
- Logout returns to login page

### TC-NAV-002: State Management
**Priority:** Medium  
**Description:** Verify application state management  
**Test Steps:**
1. Add items to cart
2. Sort products
3. Click Reset App State
4. Verify application state
**Expected Results:**
- Cart is cleared
- Sort returns to default
- Product page resets

## 6. Error Handling Test Cases

### TC-ERR-001: Form Validation
**Priority:** High  
**Description:** Verify form validation during checkout  
**Test Steps:**
1. Go to checkout
2. Test form with:
   - Empty fields
   - Invalid ZIP
   - Special characters
**Expected Results:**
- Appropriate error messages
- Cannot proceed with invalid data
- Validation in real-time

### TC-ERR-002: Invalid Login
**Priority:** High  
**Description:** Verify invalid login handling  
**Test Steps:**
1. Try invalid username
2. Try invalid password
3. Try empty fields
**Expected Results:**
- Clear error messages
- Cannot proceed
- User guidance provided

## 7. Performance Test Cases

### TC-PERF-001: Page Load Performance
**Priority:** Medium  
**Description:** Verify page load times  
**Test Steps:**
1. Log in as performance_glitch_user
2. Navigate through all pages
3. Measure load times
**Expected Results:**
- Pages load within acceptable time
- Loading indicators shown
- No timeout errors

### TC-PERF-002: Cart Operation Performance
**Priority:** Medium  
**Description:** Verify cart operation speed  
**Test Steps:**
1. Rapidly add/remove items
2. Quick navigation with full cart
3. Fast checkout process
**Expected Results:**
- Cart updates immediately
- No lag in calculations
- Smooth checkout process

# Sauce Demo Application Test Plan

## 1. Introduction
This test plan outlines the testing strategy for the Sauce Demo e-commerce application. The plan covers various testing aspects including functionality, usability, and performance testing.

## 2. Test Objectives
- Verify all critical user journeys function correctly
- Ensure proper handling of different user types
- Validate shopping cart functionality
- Confirm checkout process works end-to-end
- Test product sorting and filtering capabilities
- Verify proper error handling and edge cases
- Assess performance under different conditions

## 3. Test Environment
### 3.1 Application URL
- Base URL: https://www.saucedemo.com/v1/

### 3.2 Test Users
- standard_user: For normal functionality testing
- locked_out_user: For authentication error testing
- problem_user: For error handling testing
- performance_glitch_user: For performance testing

### 3.3 Test Data
- Various product combinations
- Different cart quantities
- Multiple shipping addresses
- Various payment scenarios

## 4. Test Scope

### 4.1 In Scope
1. Authentication System
   - Login functionality
   - User type handling
   - Error messages
   - Session management

2. Product Catalog
   - Product listing
   - Sorting functionality
   - Product details
   - Image loading
   - Price display

3. Shopping Cart
   - Add/Remove items
   - Quantity updates
   - Cart persistence
   - Price calculations

4. Checkout Process
   - Information entry
   - Validation
   - Order review
   - Confirmation

5. Navigation & UI
   - Menu functionality
   - Responsive design
   - Button states
   - Error messages

### 4.2 Out of Scope
- Backend API testing
- Database testing
- Security penetration testing
- Mobile app testing
- Payment gateway integration testing

## 5. Test Types

### 5.1 Functional Testing
- User authentication
- Product browsing
- Cart operations
- Checkout process
- Navigation

### 5.2 Usability Testing
- UI/UX workflows
- Error message clarity
- Navigation ease
- Button state visibility

### 5.3 Performance Testing
- Page load times
- Product image loading
- Cart updates
- Checkout process speed

### 5.4 Compatibility Testing
- Cross-browser testing
- Screen resolution testing

## 6. Risk Analysis
### 6.1 High Risk Areas
- Authentication system
- Checkout process
- Shopping cart functionality
- Payment processing
- Session management

### 6.2 Medium Risk Areas
- Product sorting
- Image loading
- Price calculations
- Form validations

### 6.3 Low Risk Areas
- Static content
- Footer links
- Product descriptions

## 7. Test Deliverables
- Test cases documentation
- Test execution reports
- Bug reports
- Test metrics
- Performance test results

## 8. Test Schedule
### 8.1 Phase 1: Test Planning
- Review requirements
- Create test plan
- Design test cases
- Set up test environment

### 8.2 Phase 2: Test Execution
- Execute functional tests
- Perform usability testing
- Conduct performance testing
- Document results

### 8.3 Phase 3: Reporting
- Compile test results
- Generate reports
- Review findings
- Make recommendations

## 9. Exit Criteria
- All planned test cases executed
- No critical or high-severity bugs open
- All major functionality verified
- Performance criteria met
- Test documentation completed

## 10. Tools and Resources
### 10.1 Testing Tools
- Web browsers (Chrome, Firefox, Safari)
- Developer tools
- Screen recording software
- Performance monitoring tools

### 10.2 Resources
- Test team
- Development team
- Test environment
- Test data

## 11. Assumptions and Dependencies
### 11.1 Assumptions
- Test environment availability
- Stable test data
- Resource availability
- Timeline flexibility

### 11.2 Dependencies
- Environment access
- Test data availability
- Tool accessibility
- Team availability