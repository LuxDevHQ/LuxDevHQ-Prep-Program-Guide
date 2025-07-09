# Complete Power BI Study Guide
*A Comprehensive Resource for Students and Self-Study*

---

## Table of Contents

1. [Introduction to Power BI](#introduction-to-power-bi)
2. [Power BI Architecture](#power-bi-architecture)
3. [Getting Started](#getting-started)
4. [Data Connection and Import](#data-connection-and-import)
5. [Power Query Editor](#power-query-editor)
6. [Data Modeling](#data-modeling)
7. [Data Analysis Expressions (DAX)](#data-analysis-expressions-dax)
8. [Visualizations](#visualizations)
9. [Reports and Dashboards](#reports-and-dashboards)
10. [Power BI Service](#power-bi-service)
11. [Advanced Topics](#advanced-topics)
12. [Best Practices](#best-practices)
13. [Common Issues and Solutions](#common-issues-and-solutions)
14. [Practice Exercises](#practice-exercises)

---

## 1. Introduction to Power BI

### What is Power BI?
Power BI is Microsoft's business intelligence (BI) tool that transforms raw data into meaningful insights through interactive visualizations and reports. It enables users to:
- Connect to various data sources
- Transform and clean data
- Create interactive visualizations
- Share insights across organizations
- Make data-driven decisions

### Key Benefits
- **User-friendly interface**: Drag-and-drop functionality
- **Real-time data**: Live dashboards and automatic refresh
- **Scalability**: From personal use to enterprise-wide deployment
- **Integration**: Works seamlessly with Microsoft ecosystem
- **Cost-effective**: Free and premium tiers available

### Power BI vs Other BI Tools
| Feature | Power BI | Tableau | QlikView |
|---------|----------|---------|----------|
| Ease of Use | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ |
| Cost | ⭐⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐ |
| Microsoft Integration | ⭐⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐ |
| Advanced Analytics | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |

---

## 2. Power BI Architecture

### Core Components

#### 2.1 Power BI Desktop
- **Purpose**: Primary development tool for creating reports and dashboards
- **Platform**: Windows desktop application (free)
- **Key Features**:
  - Data connection and transformation
  - Data modeling
  - Report creation
  - DAX formula development

#### 2.2 Power BI Service (Power BI Online)
- **Purpose**: Cloud-based platform for sharing and collaboration
- **Access**: Web browser, mobile apps
- **Key Features**:
  - Report publishing and sharing
  - Dashboard creation
  - Data refresh scheduling
  - Collaboration tools
  - Content management

#### 2.3 Power BI Mobile
- **Purpose**: Mobile access to reports and dashboards
- **Platforms**: iOS, Android, Windows Mobile
- **Key Features**:
  - Offline access
  - Touch-optimized interface
  - Push notifications
  - Location-based insights

#### 2.4 Power BI Report Server
- **Purpose**: On-premises solution for organizations with data sovereignty requirements
- **Key Features**:
  - Self-hosted reports
  - Integration with existing infrastructure
  - Hybrid cloud capabilities

### Data Flow Architecture
```
Data Sources → Power Query → Data Model → Visualizations → Reports → Dashboards
```

---

## 3. Getting Started

### 3.1 Installation and Setup

#### System Requirements
- **OS**: Windows 10 or later
- **RAM**: 4GB minimum, 8GB recommended
- **Storage**: 2GB available space
- **Processor**: 1.4 GHz or faster

#### Installation Steps
1. Download Power BI Desktop from Microsoft website
2. Run installer as administrator
3. Follow setup wizard
4. Create Microsoft account (if needed)
5. Sign in to Power BI Desktop

### 3.2 Interface Overview

#### Main Interface Elements
- **Home Ribbon**: File operations, data connections, publishing
- **Modeling Ribbon**: Relationships, calculations, data types
- **View Ribbon**: Layout options, themes, bookmarks
- **Data Pane**: Fields from connected data sources
- **Visualizations Pane**: Chart types and formatting options
- **Filters Pane**: Report, page, and visual-level filters
- **Report Canvas**: Main workspace for creating visuals

#### Navigation Tips
- Use **Ctrl+S** to save frequently
- **F11** toggles full-screen mode
- **Ctrl+G** opens "Go To Page" dialog
- **Ctrl+D** duplicates selected visual

---

## 4. Data Connection and Import

### 4.1 Data Source Types

#### File-Based Sources
- **Excel**: .xlsx, .xls files
- **CSV**: Comma-separated values
- **JSON**: JavaScript Object Notation
- **XML**: Extensible Markup Language
- **PDF**: Portable Document Format
- **Text**: Fixed-width and delimited files

#### Database Sources
- **SQL Server**: Microsoft's relational database
- **Oracle**: Enterprise database system
- **MySQL**: Open-source database
- **PostgreSQL**: Advanced open-source database
- **Access**: Microsoft desktop database

#### Cloud Services
- **Azure SQL Database**: Cloud-based SQL Server
- **SharePoint**: Microsoft collaboration platform
- **Salesforce**: CRM platform
- **Google Analytics**: Web analytics service
- **Facebook**: Social media analytics

#### Web Sources
- **Web pages**: HTML tables
- **APIs**: REST and OData services
- **SharePoint Lists**: Online collaboration data

### 4.2 Connection Methods

#### Import vs DirectQuery vs Live Connection

| Method | Data Storage | Performance | Refresh | Best For |
|--------|-------------|-------------|---------|----------|
| Import | Local cache | Fast | Scheduled | Small to medium datasets |
| DirectQuery | Source system | Variable | Real-time | Large datasets, real-time needs |
| Live Connection | Source system | Fast | Real-time | Analysis Services, Power BI datasets |

#### Connection Best Practices
- Choose Import for datasets < 1GB
- Use DirectQuery for large, frequently changing data
- Consider data security and governance requirements
- Plan for data refresh schedules

### 4.3 Data Import Process

#### Step-by-Step Guide
1. **Get Data**: Click "Get Data" button
2. **Select Source**: Choose appropriate connector
3. **Configure Connection**: Enter credentials and parameters
4. **Preview Data**: Review data structure and quality
5. **Transform Data**: Use Power Query Editor if needed
6. **Load Data**: Import into Power BI model

#### Example: Connecting to Excel
```
1. Get Data → Excel → Select file
2. Choose worksheets to import
3. Preview data structure
4. Transform if needed
5. Load into model
```

---

## 5. Power Query Editor

### 5.1 Overview
Power Query Editor is the data transformation engine in Power BI, allowing users to:
- Clean and shape data
- Merge and append tables
- Create custom columns
- Apply filters and transformations
- Handle errors and missing data

### 5.2 Interface Components

#### Main Elements
- **Queries Pane**: List of all data sources and transformations
- **Data Preview**: Shows transformed data
- **Applied Steps**: History of transformations
- **Formula Bar**: Shows M language formulas
- **Ribbon**: Transformation tools and options

### 5.3 Essential Transformations

#### Data Cleaning
```
Remove Rows:
- Remove top/bottom rows
- Remove blank rows
- Remove errors
- Remove duplicates

Column Operations:
- Rename columns
- Remove columns
- Reorder columns
- Change data types
```

#### Text Transformations
```
Format Text:
- UPPERCASE/lowercase
- Proper Case
- Trim whitespace
- Remove characters

Split Columns:
- By delimiter
- By number of characters
- By positions
- Into rows
```

#### Date/Time Operations
```
Date Transformations:
- Extract date parts (year, month, day)
- Calculate age
- Parse date formats
- Create date hierarchies
```

### 5.4 Advanced Transformations

#### Conditional Columns
```
Add Conditional Column:
IF [Sales] > 10000 THEN "High"
ELSE IF [Sales] > 5000 THEN "Medium"
ELSE "Low"
```

#### Custom Columns (M Language)
```
M Language Examples:
- Text.Combine([First Name], " ", [Last Name])
- Date.Year([Order Date])
- Number.Round([Sales Amount], 2)
```

#### Grouping and Aggregation
```
Group By Operations:
- Sum, Average, Count
- Min, Max, Standard Deviation
- Count Distinct Values
- All Rows (nested table)
```

### 5.5 Merge and Append

#### Merge Queries (JOIN)
```
Join Types:
- Inner Join: Only matching records
- Left Outer: All from left table
- Right Outer: All from right table
- Full Outer: All records from both
- Left Anti: Non-matching from left
- Right Anti: Non-matching from right
```

#### Append Queries (UNION)
```
Combine tables with same structure:
- Append as new query
- Append to existing query
- Handle column mismatches
```

### 5.6 Error Handling

#### Common Errors
- **Data Type Errors**: Wrong format conversion
- **Missing Values**: Null or blank cells
- **Connection Errors**: Source unavailable
- **Transformation Errors**: Invalid operations

#### Error Resolution
```
Error Handling Functions:
- try...otherwise
- Error.Record
- Replace errors with default values
- Remove error rows
```

---

## 6. Data Modeling

### 6.1 Fundamental Concepts

#### Data Model Structure
A well-designed data model is crucial for Power BI performance and usability. It consists of:
- **Facts**: Quantitative data (sales, revenue, quantities)
- **Dimensions**: Descriptive data (products, customers, dates)
- **Relationships**: Connections between tables
- **Hierarchies**: Drill-down paths (Year → Quarter → Month)

#### Schema Types

##### Star Schema (Recommended)
```
Central Fact Table connected to Dimension Tables
- Sales Fact ← Product Dimension
- Sales Fact ← Customer Dimension
- Sales Fact ← Date Dimension
- Sales Fact ← Store Dimension
```

##### Snowflake Schema
```
Normalized dimension tables
- Product → Category → Subcategory
- Customer → City → State → Country
```

### 6.2 Table Types

#### Fact Tables
- Contain measurable, quantitative data
- Usually have many rows
- Connected to dimension tables via foreign keys
- Examples: Sales transactions, website visits, survey responses

#### Dimension Tables
- Contain descriptive, qualitative data
- Usually have fewer rows than fact tables
- Provide context for facts
- Examples: Product catalog, customer information, date calendar

#### Bridge Tables
- Handle many-to-many relationships
- Contain foreign keys from both related tables
- Examples: Student-Course enrollments, Product-Category assignments

### 6.3 Relationships

#### Relationship Types
1. **One-to-Many (1:*)**: Most common
   - One product can have many sales
   - One customer can have many orders

2. **One-to-One (1:1)**: Rare
   - One employee has one badge
   - One country has one capital

3. **Many-to-Many (*:*)**: Requires bridge table
   - Students enroll in multiple courses
   - Products belong to multiple categories

#### Relationship Properties

##### Cardinality
- Defines how tables relate to each other
- Affects filter propagation
- Impacts performance and calculations

##### Cross-Filter Direction
- **Single**: Default, filters flow from "one" to "many" side
- **Both**: Filters flow in both directions (use cautiously)

##### Active vs Inactive
- **Active**: Used by default in calculations
- **Inactive**: Must be explicitly activated in DAX

### 6.4 Creating Relationships

#### Automatic Detection
Power BI automatically creates relationships based on:
- Column names
- Data types
- Unique values
- Foreign key patterns

#### Manual Creation
```
Steps:
1. Go to Model View
2. Drag from one table to another
3. Configure relationship properties
4. Validate with sample data
```

#### Relationship Best Practices
- Use integer keys when possible
- Ensure referential integrity
- Minimize bi-directional relationships
- Create proper date tables
- Use meaningful column names

### 6.5 Hierarchies

#### Creating Hierarchies
```
Common Hierarchies:
- Date: Year → Quarter → Month → Day
- Geography: Country → State → City
- Product: Category → Subcategory → Product
- Organization: Department → Team → Employee
```

#### Hierarchy Benefits
- Enable drill-down/drill-up functionality
- Improve user experience
- Provide natural navigation paths
- Support time intelligence functions

### 6.6 Calculated Columns vs Measures

#### Calculated Columns
- Computed for each row
- Stored in the model
- Available in slicers and axes
- Consume memory

```
Example:
Full Name = [First Name] & " " & [Last Name]
```

#### Measures
- Computed at query time
- Dynamic calculations
- Respond to filters and context
- Better performance for aggregations

```
Example:
Total Sales = SUM(Sales[Amount])
```

---

## 7. Data Analysis Expressions (DAX)

### 7.1 DAX Fundamentals

#### What is DAX?
DAX (Data Analysis Expressions) is a formula language used in Power BI for:
- Creating calculated columns
- Defining measures
- Building calculated tables
- Implementing business logic

#### DAX Syntax
```
Basic Structure:
Measure Name = FUNCTION(Table[Column])

Examples:
Total Sales = SUM(Sales[Amount])
Average Price = AVERAGE(Products[Price])
```

#### Key Concepts
- **Tables**: Collections of related data
- **Columns**: Individual fields in tables
- **Measures**: Dynamic calculations
- **Context**: Filter environment for calculations

### 7.2 DAX Functions by Category

#### 7.2.1 Aggregation Functions

##### SUM Functions
```
SUM(column): Basic sum
Total Revenue = SUM(Sales[Revenue])

SUMX(table, expression): Row-by-row sum
Total Profit = SUMX(Sales, Sales[Quantity] * Sales[Unit Price])
```

##### AVERAGE Functions
```
AVERAGE(column): Simple average
Average Sale = AVERAGE(Sales[Amount])

AVERAGEX(table, expression): Row-by-row average
Average Margin = AVERAGEX(Sales, Sales[Profit] / Sales[Revenue])
```

##### COUNT Functions
```
COUNT(column): Count non-blank values
Order Count = COUNT(Sales[OrderID])

COUNTROWS(table): Count rows in table
Total Orders = COUNTROWS(Sales)

DISTINCTCOUNT(column): Count unique values
Unique Customers = DISTINCTCOUNT(Sales[CustomerID])
```

##### MIN/MAX Functions
```
MIN(column): Minimum value
Lowest Price = MIN(Products[Price])

MAX(column): Maximum value
Highest Sale = MAX(Sales[Amount])
```

#### 7.2.2 Filter Functions

##### FILTER Function
```
FILTER(table, condition): Returns filtered table
High Value Sales = FILTER(Sales, Sales[Amount] > 1000)

Usage in measures:
Large Orders = COUNTROWS(FILTER(Sales, Sales[Amount] > 500))
```

##### CALCULATE Function
```
CALCULATE(expression, filter1, filter2, ...): Modifies filter context
West Coast Sales = CALCULATE(SUM(Sales[Amount]), Sales[Region] = "West")

Multiple filters:
Q1 Sales = CALCULATE(
    SUM(Sales[Amount]),
    Sales[Quarter] = 1,
    Sales[Year] = 2023
)
```

##### ALL Functions
```
ALL(table/column): Removes all filters
Total Sales All Regions = CALCULATE(SUM(Sales[Amount]), ALL(Sales[Region]))

ALLEXCEPT(table, column1, column2, ...): Removes all filters except specified
Sales % of Year = DIVIDE(
    SUM(Sales[Amount]),
    CALCULATE(SUM(Sales[Amount]), ALLEXCEPT(Sales, Sales[Year]))
)
```

#### 7.2.3 Logical Functions

##### IF Function
```
IF(condition, value_if_true, value_if_false)

Profit Category = IF(Sales[Profit] > 0, "Profitable", "Loss")

Nested IF:
Performance = IF(
    Sales[Amount] > 10000, "Excellent",
    IF(Sales[Amount] > 5000, "Good", "Poor")
)
```

##### SWITCH Function
```
SWITCH(expression, value1, result1, value2, result2, ..., default)

Rating = SWITCH(
    TRUE(),
    Sales[Amount] > 10000, "A",
    Sales[Amount] > 5000, "B",
    Sales[Amount] > 1000, "C",
    "D"
)
```

##### AND/OR Functions
```
AND(condition1, condition2, ...): All conditions must be true
High Value Customer = AND(
    Customer[Total Sales] > 10000,
    Customer[Order Count] > 5
)

OR(condition1, condition2, ...): Any condition can be true
VIP Customer = OR(
    Customer[Total Sales] > 50000,
    Customer[Years Active] > 10
)
```

#### 7.2.4 Date and Time Functions

##### Basic Date Functions
```
TODAY(): Current date
Current Date = TODAY()

NOW(): Current date and time
Current DateTime = NOW()

DATE(year, month, day): Create date
Custom Date = DATE(2023, 12, 31)
```

##### Date Extraction
```
YEAR(date): Extract year
Sales Year = YEAR(Sales[Date])

MONTH(date): Extract month
Sales Month = MONTH(Sales[Date])

WEEKDAY(date): Day of week (1=Sunday)
Day of Week = WEEKDAY(Sales[Date])
```

##### Time Intelligence
```
TOTALYTD(expression, date_column): Year-to-date total
YTD Sales = TOTALYTD(SUM(Sales[Amount]), Sales[Date])

SAMEPERIODLASTYEAR(date_column): Previous year period
Last Year Sales = CALCULATE(
    SUM(Sales[Amount]),
    SAMEPERIODLASTYEAR(Sales[Date])
)

DATEADD(date_column, number, interval): Shift dates
Previous Month = DATEADD(Sales[Date], -1, MONTH)
```

#### 7.2.5 Text Functions

##### String Manipulation
```
CONCATENATE(text1, text2): Join strings
Full Name = CONCATENATE(Customer[First Name], " ", Customer[Last Name])

LEFT(text, num_chars): Extract from left
First Initial = LEFT(Customer[First Name], 1)

RIGHT(text, num_chars): Extract from right
Last Two Digits = RIGHT(Product[SKU], 2)

MID(text, start_num, num_chars): Extract middle
Area Code = MID(Customer[Phone], 2, 3)
```

##### String Functions
```
LEN(text): String length
Name Length = LEN(Customer[Name])

UPPER(text): Convert to uppercase
Upper Name = UPPER(Customer[Name])

LOWER(text): Convert to lowercase
Lower Email = LOWER(Customer[Email])

TRIM(text): Remove extra spaces
Clean Name = TRIM(Customer[Name])
```

##### Search Functions
```
FIND(find_text, within_text): Find position
At Position = FIND("@", Customer[Email])

SEARCH(find_text, within_text): Case-insensitive find
Domain Start = SEARCH("@", Customer[Email]) + 1
```

#### 7.2.6 Mathematical Functions

##### Basic Math
```
ABS(number): Absolute value
Absolute Variance = ABS(Sales[Actual] - Sales[Budget])

ROUND(number, digits): Round to specified decimals
Rounded Sales = ROUND(Sales[Amount], 2)

CEILING(number): Round up
Ceiling Price = CEILING(Product[Cost] * 1.2)

FLOOR(number): Round down
Floor Price = FLOOR(Product[Cost] * 0.8)
```

##### Statistical Functions
```
STDEV.P(column): Population standard deviation
Price StdDev = STDEV.P(Product[Price])

VAR.P(column): Population variance
Sales Variance = VAR.P(Sales[Amount])

MEDIAN(column): Middle value
Median Sale = MEDIAN(Sales[Amount])

PERCENTILE.INC(column, k): Percentile value
P90 Sales = PERCENTILE.INC(Sales[Amount], 0.9)
```

### 7.3 Context in DAX

#### Row Context
- Applies to calculated columns
- Evaluates expression for each row
- Automatically created during iteration

#### Filter Context
- Applies to measures
- Determined by report filters, slicers, and visuals
- Can be modified using CALCULATE

#### Context Transition
- Conversion from row context to filter context
- Happens automatically in measures
- Can be forced using CALCULATE

### 7.4 Advanced DAX Patterns

#### Running Totals
```
Running Total = CALCULATE(
    SUM(Sales[Amount]),
    FILTER(
        ALL(Sales[Date]),
        Sales[Date] <= MAX(Sales[Date])
    )
)
```

#### Ranking
```
Sales Rank = RANKX(
    ALL(Product[Name]),
    CALCULATE(SUM(Sales[Amount]))
)
```

#### Period Comparisons
```
Sales Growth = DIVIDE(
    SUM(Sales[Amount]) - CALCULATE(
        SUM(Sales[Amount]),
        DATEADD(Sales[Date], -1, YEAR)
    ),
    CALCULATE(
        SUM(Sales[Amount]),
        DATEADD(Sales[Date], -1, YEAR)
    )
)
```

#### Moving Averages
```
3-Month Moving Average = CALCULATE(
    AVERAGE(Sales[Amount]),
    DATESINPERIOD(
        Sales[Date],
        MAX(Sales[Date]),
        -3,
        MONTH
    )
)
```

---

## 8. Visualizations

### 8.1 Chart Types and When to Use Them

#### Column and Bar Charts
**Best for**: Comparing values across categories

```
Column Chart:
- Vertical bars
- Good for time series
- Compare multiple categories

Bar Chart:
- Horizontal bars
- Better for long category names
- Easy to read values
```

**Use Cases**:
- Sales by region
- Monthly revenue trends
- Product performance comparison

#### Line Charts
**Best for**: Showing trends over time

```
Line Chart:
- Continuous data
- Time series analysis
- Multiple metrics comparison

Area Chart:
- Filled line chart
- Shows cumulative values
- Good for part-to-whole relationships
```

**Use Cases**:
- Stock price movements
- Website traffic over time
- Sales trends by quarter

#### Pie and Donut Charts
**Best for**: Part-to-whole relationships (with limitations)

```
Pie Chart:
- Maximum 7 categories
- Shows proportions
- Easy to understand

Donut Chart:
- Similar to pie chart
- Central space for additional info
- More modern appearance
```

**Use Cases**:
- Market share distribution
- Budget allocation
- Customer segments

#### Scatter Plots
**Best for**: Showing relationships between two continuous variables

```
Scatter Plot:
- X and Y axes with continuous data
- Shows correlation
- Can include size and color dimensions

Bubble Chart:
- Scatter plot with size dimension
- Three variables at once
- Good for complex relationships
```

**Use Cases**:
- Price vs. sales volume
- Customer satisfaction vs. loyalty
- Risk vs. return analysis

### 8.2 Advanced Visualizations

#### Matrix (Pivot Table)
```
Features:
- Rows and columns grouping
- Drill-down capabilities
- Conditional formatting
- Subtotals and grand totals

Best for:
- Cross-tabulation analysis
- Detailed data exploration
- Financial reporting
```

#### Treemap
```
Features:
- Hierarchical data representation
- Size represents one measure
- Color represents another measure
- Interactive drill-down

Best for:
- Portfolio analysis
- Budget visualization
- Website analytics
```

#### Waterfall Chart
```
Features:
- Shows cumulative effect
- Positive and negative changes
- Running total visualization

Best for:
- Profit and loss analysis
- Budget variance
- Cash flow analysis
```

#### Funnel Chart
```
Features:
- Sequential process visualization
- Conversion rates
- Bottleneck identification

Best for:
- Sales pipeline
- Website conversion
- Process optimization
```

### 8.3 Custom Visuals

#### Importing Custom Visuals
1. Go to AppSource
2. Search for required visual
3. Add to Power BI
4. Use in reports

#### Popular Custom Visuals
- **Word Cloud**: Text frequency visualization
- **Gantt Chart**: Project timeline
- **Sunburst**: Hierarchical data
- **Radar Chart**: Multi-dimensional comparison

### 8.4 Formatting and Design

#### Color Theory
```
Color Guidelines:
- Use consistent color palette
- Ensure accessibility (color blindness)
- Maintain brand consistency
- Use color to highlight key insights
```

#### Typography
```
Font Best Practices:
- Maximum 2-3 font families
- Consistent font sizes
- Good contrast ratios
- Readable font choices
```

#### Layout Principles
```
Design Principles:
- Alignment: Create visual connections
- Proximity: Group related elements
- Contrast: Emphasize important information
- Repetition: Maintain consistency
```

### 8.5 Interactive Features

#### Slicers
```
Slicer Types:
- List: Traditional dropdown
- Dropdown: Space-saving option
- Between: Range selection
- Before/After: Date filtering
- Relative Date: Dynamic date ranges
```

#### Bookmarks
```
Bookmark Uses:
- Save specific report states
- Create navigation between views
- Build story-telling sequences
- Implement button actions
```

#### Drill-Through
```
Drill-Through Setup:
1. Create destination page
2. Add drill-through field
3. Configure source visuals
4. Test navigation
```

#### Tooltips
```
Tooltip Features:
- Show additional context
- Custom tooltip pages
- Rich formatting options
- Interactive elements
```

---

## 9. Reports and Dashboards

### 9.1 Report Design Principles

#### Information Hierarchy
```
Visual Hierarchy:
1. Primary KPIs (top/center)
2. Supporting metrics
3. Detailed analysis
4. Filters and controls
```

#### User Experience
```
UX Considerations:
- Clear navigation
- Consistent layout
- Responsive design
- Fast loading times
- Intuitive interactions
```

#### Storytelling with Data
```
Story Structure:
1. Context: What's the situation?
2. Conflict: What's the problem?
3. Resolution: What's the solution?
4. Action: What should be done?
```

### 9.2 Report Types

#### Executive Dashboard
```
Characteristics:
- High-level KPIs
- Minimal detail
- Visual appeal
- Real-time updates
- Exception highlighting
```

#### Operational Report
```
Characteristics:
- Detailed data
- Drill-down capabilities
- Regular updates
- Process monitoring
- Performance tracking
```

#### Analytical Report
```
Characteristics:
- Deep analysis
- Statistical insights
- Trend identification
- Comparative analysis
- Predictive elements
```

### 9.3 Performance Optimization

#### Report Performance
```
Optimization Techniques:
- Minimize visual count
- Use appropriate chart types
- Optimize DAX calculations
- Implement proper filtering
- Use aggregated data when possible
```

#### Data Model Performance
```
Model Optimization:
- Use star schema
- Minimize calculated columns
- Implement proper relationships
- Use appropriate data types
- Remove unnecessary columns
```

### 9.4 Mobile Optimization

#### Mobile Layout
```
Mobile Design:
- Portrait orientation
- Touch-friendly controls
- Simplified navigation
- Larger fonts and buttons
- Condensed information
```

#### Responsive Design
```
Responsive Features:
- Automatic scaling
- Flexible layouts
- Conditional formatting
- Mobile-specific visuals
- Touch interactions
```

---

## 10. Power BI Service

### 10.1 Publishing and Sharing

#### Publishing Reports
```
Publishing Process:
1. Complete report in Power BI Desktop
2. Click "Publish" button
3. Select destination workspace
4. Configure refresh settings
5. Share with stakeholders
```

#### Sharing Options
```
Sharing Methods:
- Direct sharing with individuals
- Workspace collaboration
- App distribution
- Public embedding
- Secure embedding
```

### 10.2 Workspaces

#### Workspace Types
```
My Workspace:
- Personal development area
- Limited sharing capabilities
- Testing and prototyping

Standard Workspace:
- Team collaboration
- Role-based access
- Content management
- Version control
```

#### Workspace Roles
```
Roles and Permissions:
- Admin: Full control
- Member: Create and edit content
- Contributor: Edit existing content
- Viewer: Read-only access
```

### 10.3 Data Refresh

#### Refresh Types
```
Refresh Options:
- Manual refresh
- Scheduled refresh
- Real-time streaming
- DirectQuery (live connection)
```

#### Refresh Configuration
```
Setup Process:
1. Configure data source credentials
2. Set refresh schedule
3. Configure failure notifications
4. Monitor refresh history
5. Troubleshoot issues
```

### 10.4 Security and Governance

#### Row-Level Security (RLS)
```
RLS Implementation:
1. Define security roles
2. Create DAX filters
3. Assign users to roles
4. Test security settings
5. Monitor access
```

#### Data Classification
```
Sensitivity Labels:
- Public
- Internal
- Confidential
- Highly Confidential
```

---

## 11. Advanced Topics

### 11.1 Advanced DAX

#### Table Functions
```
SUMMARIZE: Create summary tables
Summary Table = SUMMARIZE(
    Sales,
    Sales[Product],
    Sales[Region],
    "Total Sales", SUM(Sales[Amount])
)

ADDCOLUMNS: Add calculated columns
Extended Table = ADDCOLUMNS(
    Products,
    "Sales Amount", CALCULATE(SUM(Sales[Amount]))
)
```

#### Variables in DAX
```
Variable Usage:
Sales Variance = 
VAR CurrentSales = SUM(Sales[Amount])
VAR PreviousSales = CALCULATE(
    SUM(Sales[Amount]),
    DATEADD(Sales[Date], -1, YEAR)
)
RETURN
DIVIDE(CurrentSales - PreviousSales, PreviousSales)
```

### 11.2 Custom Visuals Development

#### R Visuals
```
R Integration:
- Statistical analysis
- Advanced charting
- Machine learning models
- Custom calculations
```

#### Python Visuals
```
Python Integration:
- Data science libraries
- Machine learning
- Advanced analytics
- Custom visualizations
```

### 11.3 Power BI APIs

#### REST API
```
API Capabilities:
- Embed reports
- Manage workspaces
- Refresh datasets
- Export reports
- User management
```

#### Embedding
```
Embedding Options:
- User owns data
- App owns data
- Secure embedding
- Public embedding
```

### 11.4 Advanced Analytics

#### Quick Insights
```
Automatic Insights:
- Trend detection
- Anomaly identification
- Pattern recognition
- Correlation analysis
```

#### AI Visuals
```
AI Features:
- Key influencers
- Decomposition tree
- Q&A visual
- Smart narrative
```

---

## 12. Best Practices

### 12.1 Data Model Best Practices

#### Design Principles
```
Model Design:
✅ Use star schema
✅ Create proper relationships
✅ Use meaningful names
✅ Implement date tables
✅ Optimize data types

❌ Avoid snowflake schema
❌ Don't use calculated columns for aggregations
❌ Avoid bi-directional relationships
❌ Don't ignore data quality
❌ Avoid complex many-to-many relationships
```
