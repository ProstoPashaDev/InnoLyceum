# Quality Attribute Scenarios

## Functional Suitability

### Functional Appropriateness

**Why it's important to the customer:**  
The lyceum’s users (students, parents, applicants) rely on the website to complete essential tasks like accessing documents, information about upcoming events, news and information for applicants. If the site’s functionality isn’t aligned with their actual needs, the platform will be frustrating and underused.

#### Test: Admin Staff Access and Download Required Documents

#### Test ID: FAP13

| Element            | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Source**         | Administrative staff                                                        |
| **Stimulus**       | Staff member visits the website, uses the header dropdown to access the "Documents" page, and attempts to download a needed form. |
| **Artifact**       | Navigation menu, "Documents" page, download links                           |
| **Environment**    | Live production environment (desktop browser)                               |
| **Response**       | Page loads correctly, document is found and successfully downloaded         |
| **Response Measure** | Staff completes task in ≤30 seconds with no broken links or incorrect files |

**Execution Method:**  
This is an **integration test**.

We will use an automated browser testing framework (e.g., **Playwright** or **Selenium**) to:

1. Simulate login as an admin user.  
2. Navigate via the site header to the "Documents" page.  
3. Verify that:  
   - The correct URL is reached.  
   - All listed files are visible.  
   - Each download link returns a file with expected MIME type and size.

This test will be integrated into the CI pipeline to run on every deployment.

## Maintainability

### Modifiability

**Why it's important to the customer:**  
Non-technical staff (teachers, administrators) will manage most of the site’s content. They must be able to update text, documents, and menus; publish news and information for upcoming events without developer help and without breaking anything.

#### Test: Admin Adds New Event via CMS

#### Test ID: MOD92

| Element            | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Source**         | Lyceum administrative staff                                                 |
| **Stimulus**       | Admin logs into CMS and creates a new event with title, text, time/date, place, and photo. |
| **Artifact**       | CMS event module, main page event block, and events page                    |
| **Environment**    | CMS backend, live or staging site                                           |
| **Response**       | New event is saved and displayed correctly both on the homepage and the events page. No layout issues or broken media. |
| **Response Measure** | Admin completes the task in ≤10 minutes. Event visible on both pages within 1 minute after saving. Layout remains intact on desktop and mobile. |

**Execution Method:**  
This is an **integration test**, supported by **unit tests**.

1. **Unit tests** for CMS components (e.g., `EventForm`, `ImageUpload`, `EventService`) will verify:  
   - Validation of inputs (e.g., date format, image size).  
   - Database interactions (event creation and update).

2. **Integration test** simulates:  
   - Admin login.  
   - Event creation via the CMS UI.  
   - Verification that the event appears on:  
     - The homepage.  
     - The full events listing page.  
   - Image is loaded successfully and is responsive.

## Reliability

### Availability

**Why it's important to the customer:** 
The website needs to be consistently available so users can access time-sensitive content like information for applicants, announcements of upcoming events, especially during peak traffic.

#### Test: Maintain Availability During Peak Access

#### Test ID: AVB12

| Element            | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Source**         | Students and parents                                                        |
| **Stimulus**       | 200 users attempt to access the homepage.                                   |
| **Artifact**       | Web server, CMS backend, Nginx                                              |
| **Environment**    | Staging server using load testing tools (e.g., k6, Apache JMeter, Postman)  |
| **Response**       | The website remains online, all pages load correctly, and no errors are encountered. |
| **Response Measure** | ≥95% of requests respond in <2 seconds, 0 failed requests.                |

**Execution Method:**  
This is a **non-functional integration test** using **load testing tools**.

1. Use tool like **k6**, **Apache JMeter**, **Postman** to simulate 200 concurrent users accessing:  
   - Homepage  
   - Documents page  
   - Events page

2. Record and analyze:
   - Error rate  
   - Average response time
