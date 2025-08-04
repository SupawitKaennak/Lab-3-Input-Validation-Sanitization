# Lab 3: Input Validation & Sanitization

## 🎯 Objectives
This lab demonstrates client-side input validation and sanitization techniques to prevent security vulnerabilities and ensure data integrity.

## 🔒 Security Features

### Input Validation
- **Email Validation**: Ensures proper email format using regex
- **Password Strength**: Requires minimum 8 characters with uppercase, lowercase, and number
- **Username Validation**: 3-20 characters, alphanumeric and underscore only
- **Phone Validation**: Supports Thai phone number format (0812345678 or +66812345678)
- **Age Validation**: Range validation (1-120 years)
- **URL Validation**: Validates website URLs
- **Real-time Feedback**: Instant validation as user types

### Input Sanitization
- **HTML Entity Encoding**: Converts `<`, `>`, `"`, `'` to safe HTML entities
- **XSS Prevention**: Demonstrates how malicious HTML/JavaScript is neutralized
- **Live Sanitization Preview**: Shows original vs sanitized input

## 🚀 Features

### Interactive Form
- Real-time validation feedback
- Visual indicators (green/red borders)
- Password strength meter
- Form submission with comprehensive validation
- Clear form functionality

### Validation Results Panel
- Live status of all form fields
- Visual validation indicators
- Comprehensive error messages

### Sanitization Demo
- Real-time HTML sanitization preview
- Shows how malicious input is cleaned
- Educational demonstration of XSS prevention

## 🛠️ Technical Implementation

### Core Functions
```javascript
// Email validation
function validateEmail(email) {
    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return emailRegex.test(email);
}

// Password validation
function validatePassword(password) {
    const passwordRegex = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)[a-zA-Z\d@$!%*?&]{8,}$/;
    return passwordRegex.test(password);
}

// Input sanitization
function sanitizeInput(input) {
    return input.trim()
                .replace(/</g, '&lt;')
                .replace(/>/g, '&gt;')
                .replace(/"/g, '&quot;')
                .replace(/'/g, '&#39;');
}
```

## 🧪 Testing Examples

### Valid Input Examples
- **Username**: `test123`, `user_name`, `MyUser123`
- **Email**: `test@example.com`, `user.name@domain.co.uk`
- **Password**: `TestPass123`, `SecureP@ss1`
- **Phone**: `0812345678`, `+66812345678`
- **Age**: `25`, `18`, `65`
- **Website**: `https://example.com`, `http://www.test.org`

### Invalid Input Examples
- **Username**: `ab`, `user@name`, `verylongusername123456789`
- **Email**: `invalid-email`, `test@`, `@domain.com`
- **Password**: `weak`, `password`, `12345678`
- **Phone**: `123`, `abc123def`, `081234567890`
- **Age**: `0`, `150`, `abc`

### XSS Test Cases
Try entering these in the Bio field to see sanitization in action:
- `<script>alert('XSS')</script>`
- `<img src=x onerror=alert('XSS')>`
- `<a href="javascript:alert('XSS')">Click me</a>`
- `<div onclick="alert('XSS')">Click me</div>`

## 🎨 UI/UX Features

### Visual Design
- Modern gradient background
- Responsive grid layout
- Smooth animations and transitions
- Color-coded validation feedback
- Professional form styling

### User Experience
- Real-time validation feedback
- Clear error messages
- Password strength visualization
- Form reset functionality
- Success/error notifications

## 📱 Responsive Design
- Mobile-friendly layout
- Adaptive grid system
- Touch-friendly form elements
- Optimized for all screen sizes

## 🔧 How to Use

1. **Open the Application**
   - Open `index.html` in a web browser
   - The form will load with real-time validation

2. **Test Validation**
   - Fill out form fields with various inputs
   - Watch real-time validation feedback
   - Try both valid and invalid inputs

3. **Test Sanitization**
   - Enter HTML/JavaScript in the Bio field
   - Observe how malicious code is sanitized
   - Compare original vs sanitized output

4. **Submit Form**
   - Complete all required fields correctly
   - Submit to see sanitized data output
   - Try submitting with errors to see feedback

## 🛡️ Security Benefits

### Input Validation
- Prevents invalid data entry
- Reduces server-side processing load
- Improves user experience with immediate feedback
- Ensures data quality and consistency

### Input Sanitization
- Prevents Cross-Site Scripting (XSS) attacks
- Neutralizes malicious HTML/JavaScript
- Protects against injection attacks
- Maintains data integrity

## 📚 Learning Outcomes

After completing this lab, you should understand:
- How to implement client-side input validation
- Techniques for sanitizing user input
- Common security vulnerabilities and prevention methods
- Best practices for form handling
- Real-time user feedback implementation

## 🔗 Related Topics
- Cross-Site Scripting (XSS)
- SQL Injection Prevention
- Input Validation Best Practices
- Client-Side Security
- Web Application Security

---

**Note**: This lab focuses on client-side validation and sanitization. In production applications, server-side validation and sanitization are also essential for complete security. 