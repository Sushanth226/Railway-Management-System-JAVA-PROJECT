# Contributing to Railway Management System

Thank you for your interest in contributing! This document provides guidelines and instructions for contributing to the Railway Management System project.

## Code of Conduct

Please be respectful and inclusive. We are committed to providing a welcoming and inspiring community.

## How to Contribute

### 1. Reporting Bugs

Before creating bug reports, please check the issue list as you might find out that you don't need to create one.

**When creating a bug report, please include:**
- Clear and descriptive title
- Description of the exact steps to reproduce the problem
- Specific examples to demonstrate the steps
- Description of observed behavior
- Explanation of expected behavior
- Screenshots/logs if applicable
- Your Java version and OS

### 2. Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues.

**When creating an enhancement suggestion, please include:**
- Clear and descriptive title
- Detailed description of the suggested enhancement
- Step-by-step description of the feature
- Specific examples to demonstrate the steps
- Explanation of why this enhancement would be useful

### 3. Pull Requests

#### Before You Start
1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Follow the Java coding standards (see below)

#### Making Changes
1. Make your changes in your branch
2. Write clear, descriptive commit messages
3. Keep commits atomic (one logical change per commit)
4. Test your changes thoroughly

#### Code Standards

##### Naming Conventions
```java
// Classes: PascalCase
public class TrainService { }

// Methods & Variables: camelCase
public void bookTicket() { }
private String passengerName;

// Constants: UPPER_SNAKE_CASE
public static final int MAX_PASSENGERS = 6;
```

##### Code Organization
```java
// Order of members in a class:
1. Fields (static, then instance)
2. Constructors
3. Public methods
4. Protected methods
5. Private methods
6. Inner classes
```

##### Documentation
```java
/**
 * Brief description of what the method does.
 *
 * @param paramName Description of parameter
 * @return Description of return value
 * @throws ExceptionType Description of when exception is thrown
 */
public List<Train> getAllTrains() throws DatabaseException {
    // Implementation
}
```

##### Error Handling
```java
// Always handle exceptions appropriately
try {
    // Code that might throw exception
} catch (SQLException e) {
    logger.error("Database error occurred", e);
    throw new DataAccessException("Failed to fetch trains", e);
}
```

#### Submitting Your Pull Request

1. Push your changes to your fork: `git push origin feature/your-feature-name`
2. Create a pull request against the `develop` branch
3. Provide a clear description of your changes
4. Reference any related issues
5. Ensure all tests pass and build is successful

#### PR Checklist
- [ ] My code follows the style guidelines of this project
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests passed locally with my changes

### 4. Development Setup

#### Prerequisites
- JDK 8+
- Maven 3.6+
- MySQL 5.7+
- Git

#### Setup Steps
```bash
# Clone your fork
git clone https://github.com/your-username/Railway-Management-System-JAVA-PROJECT.git
cd Railway-Management-System-JAVA-PROJECT

# Add upstream remote
git remote add upstream https://github.com/Sushanth226/Railway-Management-System-JAVA-PROJECT.git

# Create and checkout develop branch
git checkout -b develop upstream/develop

# Install dependencies
mvn clean install

# Create your feature branch
git checkout -b feature/your-feature-name
```

#### Running Tests
```bash
# Run all tests
mvn test

# Run specific test class
mvn test -Dtest=YourTestClass

# Run with coverage
mvn clean test jacoco:report
```

#### Building the Project
```bash
# Clean build
mvn clean install

# Build without tests
mvn clean install -DskipTests

# Run the application
mvn exec:java -Dexec.mainClass="com.railway.Main"
```

### 5. Commit Message Guidelines

Write clear and descriptive commit messages:

```
Short (50 chars or less) summary of changes

Detailed explanation of what changed and why. Wrap at 72 characters.
Include any relevant issue numbers like #123.

- Bullet point 1
- Bullet point 2
```

### 6. Branch Naming Convention

Use descriptive branch names:
- `feature/add-email-notifications` - New feature
- `bugfix/fix-seat-availability-issue` - Bug fix
- `docs/update-readme` - Documentation updates
- `refactor/optimize-database-queries` - Code refactoring

### 7. Testing Guidelines

#### Unit Tests
```java
@Test
public void testBookingTicket() {
    // Arrange
    Booking booking = createTestBooking();
    
    // Act
    String bookingId = bookingService.bookTicket(booking);
    
    // Assert
    assertNotNull(bookingId);
}
```

#### Test Coverage
- Aim for at least 80% code coverage
- Test both happy paths and error cases

---

Thank you for contributing! 🚂
