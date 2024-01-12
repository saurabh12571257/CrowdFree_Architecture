# CrowdFree AWS Architecture

## Overview

This repository provides an in-depth overview of the architecture used to build the "CrowdFree" application by TripAdvisor on AWS. The application focuses on helping users determine the busyness of various locations to promote social distancing.

## Table of Contents

- [Front-End](#front-end)
- [Back-End](#back-end)
- [Data Sources](#data-sources)
- [Workflow Orchestration](#workflow-orchestration)
- [EMR Processing](#emr-processing)
- [Geolocation Data Conversion](#geolocation-data-conversion)
- [Map Layer Generation](#map-layer-generation)
- [Front-End Implementation](#front-end-implementation)
- [Additional Considerations](#additional-considerations)

## Front-End

The top section of the architecture represents the front-end of the "CrowdFree" application.

## Back-End

The bottom half of the architecture focuses on the back-end, including various components and services.

## Data Sources

- Polygon data from OpenStreetMap
- Point of interest data from SafeGraph
- Anonymized geolocation data from telemetry

## Workflow Orchestration

Apache Airflow is employed for workflow orchestration, allowing scheduled jobs and efficient data processing.

## EMR Processing

Telemetry data is processed using Elastic MapReduce (EMR), utilizing hexagons (H3) for spatial indexing.

## Geolocation Data Conversion

- Data from telemetry is indexed by EMR.
- Stored in S3.
- Converted to GeoJSON format using Amazon Athena.

## Map Layer Generation

The GeoJSON layer is loaded into S3, and Mapbox is used to create a map layer, incorporating spatial information.

## Front-End Implementation

- AWS Amplify for quick setup, user authentication, and data store integration.
- Web Application Firewall for security, particularly against DDoS attacks.
- APIs backed by Amazon API Gateway, AWS Lambda, and Elasticsearch power various features, including location search.

## Additional Considerations

- DynamoDB is mentioned for potentially storing snapshot information, but details are not provided.
- The application has a search bar, date functionality, and potentially other features that interact with APIs.

## Conclusion

This repository aims to provide a comprehensive understanding of the architecture and technologies employed in building the "CrowdFree" application on AWS.

For more details, refer to the architecture review videos and explanations provided in the [videos folder](videos/).

---

Feel free to customize this template to fit your specific needs and provide additional details as necessary. You can also include links to relevant videos, diagrams, or any other resources that complement the documentation.
