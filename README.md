# Sample REST Services

This is a custom version of the Original Oracle APEX App which I have modified to:
- Implement as features from the APEX Advisor Scanner as possible
- Adjusted components with the upgrade feature
- Changed the theme to Iris
- Run the APEX Object dependencies for errors
- Add help and accessibility markers

Sample REST Services is a demonstration application that shows how Oracle APEX can consume, present, and act on data coming from REST endpoints. It brings together multiple integration styles, including Simple HTTP, ORDS, OData, synchronization, REST invocation, plug-ins, and workflow-driven processing, so developers can explore practical patterns for external service integration in a single app.

To run this application, you need an Oracle APEX environment that supports the exported app version 26.1.1, backed by an Oracle Database schema with privileges to create tables, views, procedures, and triggers for the supporting objects. The app also expects Oracle REST Data Services (ORDS) to be available for the ORDS-based examples, access to an OData endpoint for the Northwind demonstrations, outbound network access for remote REST calls, and optionally a TMDb API key for the movie-based examples that use web credentials and custom REST data source plug-ins.

## What Does the App Do?
The application starts with a guided setup flow that helps the user configure the remote ORDS base URL, schema alias, OData endpoint, and proxy details when needed. This setup is important because several pages depend on live remote services rather than only local database data.

The first functional area focuses on core REST integrations. It demonstrates how Oracle APEX can consume Simple HTTP, ORDS, and OData services, then expose that data through standard APEX components such as reports and forms. These pages show how different REST source types influence filtering, pagination, query capabilities, and update behavior.

The next area shows how REST data can be enriched inside APEX. The app combines remote payloads with local relational tables, applies post-processing SQL, and defines derived columns inside REST data profiles. This illustrates how developers can treat external JSON data as part of a broader application data model without hand-coding every transformation.

The display-focused pages demonstrate how the same REST-backed data can be rendered in different user experiences. The app includes reports, paginated views, cards, Oracle JET charts, faceted search, maps, and calendar displays, showing how APEX components can reuse REST data sources for analytics, navigation, and visualization.

The advanced section highlights more complex scenarios. It includes REST synchronization into local tables, invoking REST operations from page processes, ETL-style PL/SQL processing with email output, nested JSON handling with dynamic actions, a custom REST data source plug-in for TMDb pagination, and a workflow example that combines REST calls with Oracle APEX Workflow to create and track business processes.

## Page Map
- `0` Global Page
- `1` Home
- `2` Connection Setup
- `100` REST Integrations
- `101` Simple HTTP
- `102` ORDS
- `103` OData
- `104` Employee
- `200` Combine with Relational Data
- `201` Post Processing SQL
- `202` Derived Columns
- `300` Data Display Options
- `301` Simple Report
- `302` Report with Pagination
- `303` Report with Query
- `304` Cards Layout
- `305` Oracle JET Charts
- `306` Faceted Search
- `307` Map
- `308` Calendar
- `400` Advanced Features
- `401` REST Synchronization
- `402` Invoke API Process
- `403` Raise Salary
- `404` REST Data & PL/SQL
- `405` Nested JSON & Dynamic Actions
- `406` REST Data Source Plugins
- `407` REST and Workflow
- `408` Workflow Console
- `409` Workflow Details
- `500` Administration
- `501` Application Appearance
- `502` Reset Data
- `503` Web Credentials Settings
- `504` Network Setup
- `600` Help
- `9999` Login Page

## Supporting Objects
### Installed Objects
- `EBA_DEMO_REST_ASSIGNEES`
- `EBA_DEMO_REST_CUSTOMERS`
- `EBA_DEMO_REST_DEPARTMENT`
- `EBA_DEMO_REST_DEPT_LOCAL`
- `EBA_DEMO_REST_EMPLOYEE`
- `EBA_DEMO_REST_EMPLOYEECUSTOM`
- `EBA_DEMO_REST_ORDERITEMS`
- `EBA_DEMO_REST_ORDERS`
- `EBA_DEMO_REST_PRODUCTTABLE`
- `EBA_DEMO_REST_PURCHASEORDERS`
- `EBA_DEMO_REST_STOREORDERSUMMARY`
- `EBA_DEMO_REST_STORES`
- `EBA_DEMO_REST_TASKS`
- `EBA_DEMO_REST_TMDBCREDS`
- `EBA_DEMO_REST_TODOS`
- `DEPT_SEQ`
- `EBA_DEMO_REST_DATA_PKG`
- `EBA_DEMO_REST_ETL_PKG`

### Install Scripts
- `supporting-objects/install-scripts/sequences-objects-definition.sql`
- `supporting-objects/install-scripts/table-definition.sql`
- `supporting-objects/install-scripts/ords-definition.sql`
- `supporting-objects/install-scripts/data-installation.sql`
- `supporting-objects/install-scripts/etlprocess.sql`

### Upgrade Scripts
- No dedicated upgrade script files are included in this export. Supporting object upgrades are handled through the APEX supporting objects framework using the installed definitions in the export.

### Deinstall
- `supporting-objects/deinstall-script.sql`
