
A cube has 6 six sides.  similarly, there are many ways to present data

briefing books lets you share content offline

BI Composer is a wizard tool that lowers of complexity of creating an analysis

The highlight of this course is the dashboards

describe the foundation suite -  a rough overview of the architecture

## Business Intelligence

find data
make it legible
present it

---

####BI server 

is the computation engine that powers presentation services

relational databases are the source

####Essbase

primarly for extracting data from multi dimensional sources

####Data Sources

unstructed data is video, text, images

s = slide

s2-8

BI Presentation Server -> BI Server <- OLAP <- OLTP  

where OLAP is online analytical processing

where OLTP is online transaction processing

aside: security happens in the web Logic domain "a separate domain completely"

the BI server manages the repository

the repository is where the metadata resides

metadata also known as the Common Enterprise Information Model

"This is Oracle's secret sauce"

stored as a .rpd binary file

where .rpd is repository publishing directory

physical -> BMM (semantic layer) -> Presentation

where BMM is Business Model Mapping Layer

there is a tool called Shareplex that creates a copy of the data in the volatile system and pastes it into the ODS

where ODS is Operational Data Store

the process of transforming the data is ETL

where ETL is extract transform and load

Oracle uses Informatica for ETL

example query:
  select * FROM SALES
    WHERE REGION: "EMEA"

aside:  "a sql" is an abbreviation of "a structured query language statement"

A fact table contains rows of metrics and has one to many relationships with many peripheral dimension tables
  
###common dimensions
  'date'  
  'geo' or location

each dimension table contains many columns
  a column is known as an attribute

tables are also known as folders

again, there are two different types of tables
  fact table
    the column is known as a 'measure'
  dimension table
    a column type 'attribute'
    a column type 'hierarchical'

the alerts section has the agents
  active once you create an agent

comment on the UI for Administering Objects in the Presenation Catalog
"lots of these occur in many places, so it is quite redundant in that sense"

---

1. BI Server
2. BI Presentation Server
3. presentation services
4. Java Host
5. BI Scheduler
6. (cluster controller)

#####quiz
 2-21 true
 2-22 b - presentation services
 2-23 a - the home page

---

hands on with Answers

convention for naming analyses
  title and business function
  for example
    sales_pngl

---

###Objects that Restrict or Filter the Data

filter
selection steps
prompts
conditions

where a prompt is a special kind of filter  that interactively restricts the result set returned by an analysis; can be used to populate variables.

remember - an analysis is just a query

you can use a label to add a currency to a field
  you can also use conditional formatting
    example if less than $7,000, then font-color: red and font underlined

general trend:

  the more complex your calculation on the front end in presentation services, the poorer (slower) your performance.

  if calculations are done on the backend, query performance is not reduced.

  thought: perhaps this is why qlm reports take so long to run

the user gets to choose the precedence - the sort order

there is css support
  for example 

  if Dollars is less than 10 000 000

  then

  use this css to format the customer-region column
    color:LightSlateGray; font-size:80%;


s3-14    

it gets kind of interesting when you create an analysis from multiple different subject areas.

---

after lunch - lesson on adding filters

can create prompts

can use named filters
  allows you to reuse in new analyses

inline - always together

named - outside

---

#lecture 5 - Selecting and Grouping Data for Analyses

filters are pre aggregation
filters limit the results of preset conditions
filters use attributes and measures

selection steps are post aggregation
selection steps manipulates the retrieved results


example for some metric, the value is $50.  as more members are added in (the data goes through some transformation)...

background:  the selection steps was from 10g, and it originally let you do more complex reporting

aside Texas is modeled as a region in this example dataset, so this quote "you can choose Texas, or a state within Texas" almost makes sense...

a condition step is somewhat like a filter

useful for returning "Top 10 based on x"...so top 10 customers by Sales

aside "I'll give you more in depth on" ... part of the sentence is silent, or implied.  interesting.  or, "in depth" where "depth" I would expect depth

selection steps do not update - they only show data from the Aggregation Point - when the analyses was created.

in contrast, a filter is dynamic, and will show the most recently updated data from the analyses
  understand this better...

formatting is not usually applied to pivot tables.  do the formatting in the dashboard.

you can saved groups and calculated items as named objects and use them whenver you want

you can reference calculated items in selection steps

---

#Views - Lesson 6

textual
  title
  narrative
table
  table
  pivot
graph
  bar
  line
  pareto
  pie
  gauge 
  funnel
  line-area
  line-bar
  scatter
  bubble
  radar

best practice to not include too many pie graphs

best practice to avoid 3d charts in dashboards


















































