day three

balanced scorecard overview

*lagging* indicators

###Financial

profit
growth
return on investment ROI
market share

*leading* indicators

###Customer

customer satisfaction

###Internal Processes

time 
percent error

###Innovation, Learning, & Growth

exployee training

---

###Administering the Presentation Catalog

or, the architecture behind Oracle BI

LDAP - [Lightweight Directory Access Protocol](http://en.wikipedia.org/wiki/Lightweight_Directory_Access_Protocol)

####Weblogic Domain - LDAP Server

#####Admin Server
*Fusion Middleware
  -security
  -deployment
  -availability
*Admin Console

#####Managed Server

OBI - Oracle Business Intelligence

**OBI applications**
*BI Publisher
*RID
*BI Plugin
* etc...

#####node manager

#####System Components
1. BI Presentation
2. BI Cluster Controller
  * load balancing
3. BI Server
4. BI Scheduler
5. BI java host

OPMN - start, stop, restart

aside - to restart all components usually takes 15-20 minutes

---

####Role definitions for Oracle BI

#####BI Administrator
  -access 
  -create
  -revoke, assign

#####BI Author
  -create analyses
  -create dashboards

  this course focuses on the BI Author role

#####BI Consumer
  -access analyses (view-only)
  -access dashboards (view-only)

#####BI Analyst
  -create analyses
  -access dashboards (view-only)

---

authentication flow

user types in credentials
credentials are sent to the weblogic LDAP server

**LDAP server** has 3 data stores
  -identity
  -policy
  -credentials

**authorization**
  determines the resources that the user can access, such as
    -BI Answers
    -BI Publishers
    -etc...

**permissions**
  can be granted explicitly to a user or inherited from a group definition

  **Full Control** Includes all permissions
  **Modify** Read, write, and delete
  **Open** Read and, in the case of catalog folders, Traverse
  **Traverse** Applies only to folders, allowing movement through the folder to reach other objects or folders
  **No Access** Denies all permissions

---

###Data Migration and Repository Publishing Directory Development

**Types of Schemas**

-star
-snowflake
  *many to one relationships 


OLTP is write intensive

OLAP is historial, where you would run predicitive analytics and statistics packages like SAS

Common Enterprise Information Model

another course
  -RPD Development

BI Administration Tool
  -click file
  -select the type of mode that you want
    
  *offline
    -not connected to the BI server
    -safe to create your own repository
  
  **steps in offline mode**
  1. New Repository
  2. BI Server -- ODBC --> Data Source
  3. Import data


  *online

  aside "you import each table one at a time, usually it crashes"

  ---

  database layers:

  **physical**
  ORCL
  Connection Pool
    specify the domain source name
    identify the call source interface, which is the ODBC
  WC_CUST_D
  WC_PROD_D
  W_DAY_D
  W_BOOKING_

  then you can alias the table
   -aliasing allows you to use the same table without interfering

  **Business Model and Mapping**

  this is where you 
    create the hierarchies
      -hierarchies are usually created for GEO or TIME facts
      -then you go through and delete the facts that are not relevant
      -by default, the TIME hierarchies have Talmudic dates & Chinese Calendar dates...all possible ways of marking time
      -be sure to mention parent - child relationships

    set fact aggregations
    set variables
  
  **More on Variables**
  Session Variables
    system
    non-system

  Repository Variables
    dynamic
    static

  these variables are create in an initialization block:
    system
    non-system
    dynamic

  the variable names in the presentation server will be exactly the same as the variables presented to the user in the subject Area of Oracle BI Answers


---

  BI -> Core Application

  there you see your five system components and ESSbase

  everytime you do a deployment, a new rpd is saved.

  BI Publisher does not use RPD. (Discover is part of BI Publisher?)

  aside - anytime that you see the 'xyz' icon, it is some sort of 'properties menu'


---

###Dashboards

A dashboard is a place to present data

When you create a dashboard, there are ~10 different objects to choose from

you build the dashboard with the information consumer in mind


**Image**

**Prompt**

**Table or Pivot Table**
  *enables column and row sorting
  *DO NOT USE SCROLLING OPTION

**Graphs**
  *line-bar
    especially useful if you have 4 attributes and 2 measures


Best practice is to include 3-5 pages in a dashboard, not more than 10 pages.

---

a note:  

  analyses are catalogue objects

  charts, folders, and tables are dashboard objects

---

dashboard often follow this format

PROMPT

PIVOT TABLE

GRAPH

---

day four agenda:

1. Case Study
2. Lesson & Lab 16 - Dashboard Prompts
3. Questions from Day 3 - see questions.md
4. Agents
5. Integration
6. Briefing Books







