# Business Goals, Drivers and Requirements

## Background
In response to identified challenges and opportunities within the airline's customer service ecosystem, there is a strategic imperative to develop a cutting-edge Customer Management Platform (CMP). This innovative platform aims to revolutionize customer interactions across the entire travel journey, from ticket booking to in-flight experiences and beyond. Focused on elevating customer satisfaction and retention rates while driving increased revenue, the CMP unifies and leverages data from diverse touchpoints, enabling personalized services and proactive issue resolution. With a commitment to providing a 360-degree view of each passenger, this initiative aligns with the airline's vision to be a customer-centric organization, fostering stronger connections with passengers and optimizing operational efficiency.

## Business Goals

### Increased Revenue
The CMP aims to leverage customer data to personalize services, enhance in-flight retail, and optimize sales interactions. By understanding customer preferences and behavior, the airline seeks to increase sales conversion rates and drive additional revenue.

### Enhanced Customer Satisfaction:
The primary focus is on improving the overall customer experience by providing personalized services, addressing issues proactively, and streamlining interactions across various touchpoints. The goal is to exceed customer expectations, resulting in higher satisfaction levels.

### Customer Retention:
Through personalized attention, tailored services, and efficient issue resolution, the airline aims to enhance customer loyalty and retention. Satisfied and engaged customers are more likely to choose the airline for future travel, contributing to long-term business success.

## Business Drivers 
1. **Customer Experience Improvement:**
    Enhancing the overall customer experience is a primary driver. The CMP aims to provide a seamless and personalized journey for passengers, addressing pain points, and delighting customers at every touchpoint.

2. **Revenue Growth:**
    The CMP is designed to leverage customer data to drive additional revenue. By personalizing in-flight retail, improving sales interactions, and offering tailored services, the airline seeks to increase its overall revenue.

3. **Customer Retention and Loyalty:**
    Building and maintaining customer loyalty is a crucial driver. The CMP aims to create positive and lasting impressions, encouraging repeat business and fostering a loyal customer base.

4. **Operational Efficiency:**
    Streamlining processes and interactions across various departments (call center, check-in, cabin crew, etc.) contributes to operational efficiency. The goal is to reduce response times, improve issue resolution, and optimize resource allocation.

5. **Data-Driven Decision Making:**
    Leveraging customer data for insights and analytics is a key driver. The CMP aims to empower decision-makers with comprehensive information, enabling them to make informed choices and respond effectively to customer needs.

6. **Competitive Advantage:**
    The ability to offer personalized services and exceptional customer interactions provides a competitive edge. The CMP is a strategic driver in positioning the airline as a leader in customer service within the highly competitive aviation industry.

7. **Brand Image Enhancement:**
    Improving the overall perception of the airline's brand is a driver. Positive customer experiences contribute to a strong and favorable brand image, which, in turn, attracts new customers and retains existing ones.

8. **Agile Response to Customer Needs:**
    The CMP is designed to enable a proactive response to customer needs and concerns. This agility in addressing issues contributes to customer satisfaction and loyalty.

9. **Compliance and Security:**
    Ensuring compliance with data protection regulations is a driver. Implementing robust security measures in handling customer information is essential for maintaining trust and meeting legal requirements.

10. **Employee Empowerment:**
    Empowering employees with the tools and information they need is a driver. The CMP aims to provide call center agents, cabin crew, and other staff with a 360-degree view of customer interactions, contributing to better service delivery.

## Functional Requirements

### 1. Customer Profile Management:

1. Data Capture and Aggregation:
   - The system should allow the capture of detailed customer information, including personal details, travel history, and preferences.
   - Integration with ticket booking platforms, call center systems, check-in desks, in-flight retail, lounges, chauffeur-driven services, and baggage services for data aggregation.

2. Centralized Repository:
   - Maintain a centralized repository for storing customer data from various touchpoints and systems.

3. Segmentation Tools:
   - Provide tools for segmenting customers based on criteria such as travel history, preferences, and loyalty status.

4. Personalization Features:
   - Enable personalization of customer interactions and offers based on individual preferences.

5. Data Sharing:
   - Implement a mechanism to share profile data with strategic partners while ensuring compliance with privacy regulations and preserving customer anonymity.

### 2. Customer Interaction Management:

1. Interaction Logging:
   - Capture and log all customer interactions, including calls, emails, chats, and in-flight retail purchases.

2. Timeline View:
   - Present a chronological timeline view of each customer's interactions and transactions for easy tracking and reference.

3. Feedback Integration:
   - Integrate critical information from customer feedback data, including complaints, compliments, cases, and suggestions, into customer profiles.

### 3. Customer Order Management:

1. Preferences Capture:
   - Capture and store customer preferences related to orders, such as meal choices and seating preferences.

2. Personalization:
   - Enable personalization of future orders based on customer preferences.

3. Integration with Support:
   - Integrate with customer support and complaint handling systems to address order-related issues promptly.

### 4. Compensation Management:

1. Case Lifecycle:
   - Provide capabilities for case creation, prioritization, tracking, and updates.
   - Implement case assignment, routing, and escalation capabilities.

2. Self-Service:
   - Enable customer self-service capabilities for case management.

3. Notifications:
   - Implement notifications regarding case status and closures.

### 5. Case Management:

1. User-Friendly Interfaces:
   - Develop intuitive, multi-channel interfaces for passengers, call center agents, check-in agents, cabin crew, service management, and retail staff.

2. Navigation and Layout:
   - Design simplified navigation and clear layouts to access customer profiles and historical data.

3. Data Collection Mechanisms:
   - Implement data collection mechanisms from all touchpoints to gather information on passenger interactions, preferences, and behaviors.

4. Real-Time Processing:
   - Ensure real-time data processing and analysis to provide timely insights and responses.

5. Analytics Capabilities:
   - Integrate advanced analytics capabilities, including machine learning and predictive analytics.
   - Implement sentiment analysis of customer feedback and social media mentions to gauge passenger satisfaction.
   - Provide the capability to envisage various actions for specific customers and choose the best possible option to implement.

### 6. Customer Analytics Capabilities:

1. Authentication and Authorization:
   - Implement right authentication and authorization mechanisms.
   - Support Role-Based Access Control (RBAC) and Multi-Factor Authentication (MFA).

2. Security and Compliance:
   - Ensure sensitive data is encrypted at rest and during transit.
   - Conform to GDPR, PCIDSS, and other regulatory requirements.

3. Logging and Auditing:
   - Implement comprehensive logging and auditing of all customer data access and modifications.

## Actor Overview

### 1. **Customer Affairs**
   - **Role:** Responsible for managing customer relationships, addressing complaints, and ensuring customer satisfaction.
   - **Interactions with the Platform:**
     - Access customer profiles and interaction history.
     - Monitor and resolve customer complaints.
     - Provide feedback to improve customer experience.

### 2. **Skywards/Loyalty**
   - **Role:** Manages the airline's loyalty program, focusing on passenger retention and rewards.
   - **Interactions with the Platform:**
     - Access loyalty program data for personalized customer interactions.
     - Monitor and analyze loyalty program performance.

### 3. **Corporate Communications**
   - **Role:** Manages external communication and brand reputation.
   - **Interactions with the Platform:**
     - Access customer feedback and sentiments.
     - Monitor customer satisfaction metrics.

### 4. **Sales**
   - **Role:** Focuses on revenue generation through ticket sales and in-flight retail.
   - **Interactions with the Platform:**
     - Access passenger preferences and historical sales data.
     - Utilize customer insights for targeted sales strategies.

### 5. **Contact Center**
   - **Role:** Handles customer inquiries, complaints, and support.
   - **Interactions with the Platform:**
     - Access comprehensive customer profiles for effective issue resolution.
     - Utilize knowledge base for addressing customer queries.

### 6. **Marketing**
   - **Role:** Develops marketing strategies and promotions.
   - **Interactions with the Platform:**
     - Access customer data for targeted marketing campaigns.
     - Monitor the effectiveness of marketing initiatives.

### 7. **In-flight Retail**
   - **Role:** Manages sales and customer experience during flights.
   - **Interactions with the Platform:**
     - Access passenger preferences and purchase history.
     - Optimize in-flight retail offerings based on customer data.

### 8. **Catering**
   - **Role:** Manages in-flight meals and services.
   - **Interactions with the Platform:**
     - Access dietary preferences and feedback.
     - Coordinate with other departments for a seamless service.

### 9. **Service Delivery**
   - **Role:** Ensures quality service delivery across various touchpoints.
   - **Interactions with the Platform:**
     - Monitor customer satisfaction metrics.
     - Access customer profiles for personalized service.

### 10. **Commercial**
   - **Role:** Focuses on overall business strategy and revenue optimization.
   - **Interactions with the Platform:**
     - Access comprehensive data for strategic decision-making.

### 11. **Airport Operations**
   - **Role:** Manages airport-related services and logistics.
   - **Interactions with the Platform:**
     - Coordinate with other departments for a smooth passenger experience.

### 12. **Chauffer Driven Services**
   - **Role:** Manages ground transportation services.
   - **Interactions with the Platform:**
     - Access passenger preferences and booking history.

### 13. **Passengers**
   - **Role:** End-users of the airline services.
   - **Interactions with the Platform:**
     - Utilize self-service features for check-in and other services.
     - Provide feedback for continuous improvement.

### 14. **Cabin Crew**
   - **Role:** Provides in-flight services and sales.
   - **Interactions with the Platform:**
     - Access passenger profiles for personalized interactions.
     - Report and address customer issues during flights.

### 15. **Check-in Agents**
   - **Role:** Assists passengers during the check-in process.
   - **Interactions with the Platform:**
     - Access passenger profiles for a smoother check-in experience.
     - Receive alerts for special considerations.

### 16. **Baggage Services**
   - **Role:** Manages baggage handling and services.
   - **Interactions with the Platform:**
     - Access information on lost or delayed luggage.
     - Coordinate with other departments for issue resolution.

### 17. **Vendors/Partners**
   - **Role:** External entities providing services to the airline.
   - **Interactions with the Platform:**
     - Coordinate with the airline for seamless service delivery.
     - Access relevant data for collaboration.

## System Integrations
1. **Loyalty Platform Integration:**
   - *Objective:* Enhance customer loyalty and engagement.
   - *Integration Points:*
      - Seamless data exchange with the Loyalty Platform to access and update passenger loyalty information.
      - Real-time synchronization of customer preferences and reward points.

2. **Booking Systems Integration (Online and Agent Platforms):**
   - *Objective:* Streamline ticket booking processes and enhance personalized offerings.
   - *Integration Points:*
      - Integration with online booking systems to capture and update customer information.
      - Collaboration with agent platforms for a unified view of customer data across all booking channels.

3. **Contact Centre System Integration:**
   - *Objective:* Improve customer service and issue resolution.
   - *Integration Points:*
      - Direct connectivity with the Contact Centre System for real-time access to customer profiles during interactions.
      - Automated logging of customer complaints and feedback into the Customer Management Platform.

4. **Passenger Reservation System Integration:**
   - *Objective:* Ensure accurate and up-to-date passenger information.
   - *Integration Points:*
      - Bi-directional synchronization with the Passenger Reservation System for real-time updates on flight changes, seat preferences, and special requests.

5. **Inflight Retail and Meal Order System Integration:**
   - *Objective:* Enhance the inflight shopping experience and cater to passenger preferences.
   - *Integration Points:*
      - Integration with the Inflight Retail System for access to passenger purchase history and preferences.
      - Coordination with the Meal Order System to customize food and beverage options based on passenger choices.

6. **Offer Management System Integration:**
   - *Objective:* Optimize personalized offers to passengers.
   - *Integration Points:*
      - Collaboration with the Offer Management System to tailor promotions and discounts based on customer profiles.
      - Real-time adjustment of offers to align with passenger preferences and behaviors.

7. **Marketing Management System Integration:**
   - *Objective:* Improve targeted marketing strategies.
   - *Integration Points:*
      - Integration with the Marketing Management System for analyzing customer behavior and preferences.
      - Utilization of customer insights to create personalized marketing campaigns.

8. **Agent-based and Self-Service Check-in Systems Integration:**
   - *Objective:* Streamline check-in processes and enhance passenger experience.
   - *Integration Points:*
      - Collaboration with agent-based check-in systems for a unified customer check-in experience.
      - Integration with self-service check-in systems for a seamless transition of customer data.

9. **Knowledge Base Integration for Support Agents:**
   - *Objective:* Empower support agents with relevant information for issue resolution.
   - *Integration Points:*
      - Seamless access to a centralized Knowledge Base for quick retrieval of information during customer interactions.
      - Automatic updates of the Knowledge Base with new insights gathered from customer interactions.

10. **Baggage Management and Handling Systems Integration:**
    - *Objective:* Ensure efficient baggage services and issue resolution.
    - *Integration Points:*
       - Real-time synchronization with Baggage Management Systems to track and update the status of passenger luggage.
       - Automated notification of baggage-related issues to relevant departments for prompt resolution.

## Architecturally Significant Business Requirements
### Unified Customer Profile:

- The platform should provide a unified customer profile that consolidates information from various touchpoints, including ticket booking platforms, call centers, check-in desks, in-flight retail, and other relevant sources.
- Customer profiles should include historical data, preferences, past interactions, and feedback to offer a holistic view of each passenger.

### Real-time Data Synchronization:

- Ensure real-time synchronization of customer data across all integrated systems, allowing agents and staff to access the most up-to-date information.
- Changes made in one system (e.g., booking platform, call center) should be reflected seamlessly across all other connected systems.

### Integration with Loyalty Platform:

- Integrate with the loyalty platform to capture and leverage customer loyalty data, including tier status, points, and special privileges. This integration should facilitate personalized interactions and promotions.

### Seamless Booking System Integration:

- Integrate with online and agent-based booking systems to capture booking history, seat preferences, and any special requests made by the passenger.
- Enable a seamless experience for customers across various booking channels.

### Comprehensive Call Center Integration:

- Integrate with the contact center system to provide agents with a 360-degree view of customer profiles, enabling efficient issue resolution and reducing the time required to handle complaints.

### Knowledge Base Integration:

- Integrate with a knowledge base system that supports support agents in accessing relevant information and solutions when addressing complaints or queries.
- Ensure that the knowledge base is regularly updated with the latest information.

### Check-in Systems Integration:

- Integrate with both agent-based and self-service check-in systems to provide check-in agents with relevant customer information, including previous flight experiences and any special considerations.

### In-flight Retail and Meal Order Integration:

- Integrate with in-flight retail and meal order systems to capture passenger preferences and purchase history.
- Enable cabin crew members to provide personalized recommendations and improve sales conversion rates.

### Baggage Management System Integration:

- Integrate with baggage management and handling systems to track the status and location of passengers' luggage.
- Provide real-time updates to passengers and customer service agents in case of any issues.

### Chauffer Driven Services Integration:

- Integrate with chauffeur-driven services to capture passenger preferences, past usage, and any special requirements.
- Ensure a seamless and personalized experience for passengers using chauffeur-driven services.

### Security and Compliance:

- Implement robust security measures to safeguard customer data and ensure compliance with data protection regulations.
- Define access controls and authentication mechanisms to restrict access to sensitive customer information.

### Analytics and Reporting:

- Implement analytics tools to track customer satisfaction metrics, sales conversion rates, and other key performance indicators.
- Provide comprehensive reporting capabilities for different stakeholders, including Customer Affairs, Sales, Marketing, and Airport Operations.

##
| Architecturally Significant Business Requirement                                           | Business Drivers                                      |
| ------------------------------------------------------------ | ------------------------------------------------------ |
| Unified Customer Profile                                      | Customer Experience Improvement, Customer Retention and Loyalty, Operational Efficiency, Data-Driven Decision Making, Agile Response to Customer Needs, Employee Empowerment |
| Seamless Booking System Integration                             | Revenue Growth, Customer Retention and Loyalty, Competitive Advantage, Brand Image Enhancement |
| Integration with Loyalty Platform                               | Customer Retention and Loyalty, Data-Driven Decision Making |
| Real-time Data Synchronization                                   | Customer Experience Improvement, Operational Efficiency, Data-Driven Decision Making, Agile Response to Customer Needs, Employee Empowerment |
| Comprehensive Call Center Integration                         | Customer Experience Improvement, Operational Efficiency, Data-Driven Decision Making, Employee Empowerment |
| Knowledge Base Integration                                     | Customer Experience Improvement, Operational Efficiency, Data-Driven Decision Making, Employee Empowerment |
| Check-in Systems Integration                                      | Customer Experience Improvement, Operational Efficiency, Employee Empowerment |
| In-flight Retail and Meal Order Integration                  | Revenue Growth, Customer Retention and Loyalty, Competitive Advantage |
| Baggage Management System Integration                     | Customer Experience Improvement, Operational Efficiency, Agile Response to Customer Needs, Employee Empowerment |
| Chauffer Driven Services Integration                           | Revenue Growth, Customer Retention and Loyalty, Agile Response to Customer Needs, Employee Empowerment |
| Analytics and Reporting                                           | Revenue Growth, Operational Efficiency                  |
| Brand Image Enhancement                                      | Competitive Advantage, Brand Image Enhancement          |
| Security and Compliance                                           | Compliance and Security                                |

# Requirements and Engagement model

## Engagement Models


## Architecturally Significant Business Requirements

| # | Significant Architectural Requirements | Business Goal |
|----|----|----|
| 1 | Customer profiles | 1 |
| 2 | Geographical trend analysis  | 1 |
| 3 | Community engagement  | 1 |
| 4 | eDietician advice & interaction  | 2 |
| 5 | Improve food Distribution  |  |
| 6 | Medical profile information  | 3 |
| 7 | Profile customization  | 1 |
| 8 | Third party relationships   | 2 |
| 9 | Holistic UX   | 1, 2 |
| 10 | Customer engagement   |  2 |

## Significant Non-Functional requirements 
