# Automated Tests

We use **Pytest** as the primary testing framework for this project.

## Types of Tests Implemented

- **Unit tests**: 10 tests covering individual functions and components to ensure correctness at the smallest scope.
- **Integration tests**: 10 tests verifying the interaction between components and external systems such as the CMS and database.

## Location of Tests

All unit and integration tests are located in:  
`innolyceum/lyceum/mainpage/tests/unit_tests.py`

## Unit Tests

### 1. Homepage endpoint returns 200
- **Purpose**: Verify the root URL ('/') returns HTTP 200
- **Test**: Checks response status code for homepage access

### 2. Events endpoint returns 200  
- **Purpose**: Confirm events page ('/events/') loads successfully
- **Test**: Validates HTTP 200 response for events page

### 3. Wagtail admin endpoint requires authentication  
- **Purpose**: Ensure admin panel requires login
- **Test**: Verifies unauthenticated access redirects to login (HTTP 302)

### 4. AJAX events endpoint returns JSON  
- **Purpose**: Test events API endpoint
- **Test**: Confirms response contains valid JSON with 'events' key

### 5. News endpoint returns 200  
- **Purpose**: Verify news page accessibility
- **Test**: Checks HTTP 200 response for '/news/'

### 6. About Lyceum page endpoint returns 200  
- **Purpose**: Validate about page content
- **Test**: Confirms page contains director's name

### 7. Staff page renders correctly  
- **Purpose**: Test staff page display
- **Test**: Verifies teacher section title exists

### 8. Achievements page returns 200  
- **Purpose**: Check achievements page
- **Test**: Confirms title section displays correctly

### 9. Sponsorship page returns 200  
- **Purpose**: Validate sponsorship page
- **Test**: Checks for donation form presence

### 10. Schedule page returns 200  
- **Purpose**: Test schedule page
- **Test**: Verifies correct heading exists

## Integration Tests

### 1. Homepage integration with database  
- **Purpose**: Test homepage-database integration  
- **Test**: Verifies FAQ and roadmap elements load from DB

### 2. Admin login flow  
- **Purpose**: Test complete admin authentication  
- **Test**: Covers login, redirects, and admin section access

### 3. Add new event page to Wagtail  
- **Purpose**: Test event creation workflow  
- **Test**: Creates/publishes event and verifies listing

### 4. Events page displays database content  
- **Purpose**: Validate event data display  
- **Test**: Confirms events from DB appear on page

### 5. Cache integration with admin data  
- **Purpose**: Test caching system  
- **Test**: Compares response times for cached vs uncached requests

### 6. Add new news page to Wagtail  
- **Purpose**: Test news creation workflow  
- **Test**: Creates news page with images and verifies display

### 7. Navigation from main page via header  
- **Purpose**: Test homepage navigation  
- **Test**: Verifies all header links work correctly

### 8. Navigation from news page via header  
- **Purpose**: Test news page navigation  
- **Test**: Checks all header links from news page

### 9. Navigation from events page via header  
- **Purpose**: Test events page navigation  
- **Test**: Validates all header links from events page

### 10. Navigation from sponsorship page via header  
- **Purpose**: Test sponsorship page navigation  
- **Test**: Confirms all header links work properly