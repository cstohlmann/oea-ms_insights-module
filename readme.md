# Microsoft Insights Module
Microsoft Insights is a broad service that can provide School Information System (SIS) data through School Data Sync (SDS), in combination with Microsoft 365 (M365) and Microsoft Teams data, to holistically collect student interactions with Microsoft products. This module provides a set of assets for the processing of roster and application usage data received from M365 via [Azure Data Share](https://docs.microsoft.com/en-us/azure/data-share/overview#:~:text=%20Azure%20Data%20Share%20enables%20data%20providers%20to%3A,or%20allow%20them%20to%20automatically%20receive...%20See%20More.).

You can use this OEA Microsoft Insights module to incorporate these datasets into your organization's OEA data lakes.

<p align="center">
  <img src="https://github.com/cstohlmann/oea-ms_insights-module/blob/main/docs/images/insights%20visual.png?raw=true" alt="Microsoft Insights Visual"/>
</p>

  <p align="center">
 <em>
 (Microsoft documentation on Insights: https://docs.microsoft.com/en-us/microsoftteams/class-insights) 
 </em>
 </p>
 
## Problem Statement
As education systems continuously progress to digital learning methods, it is significant to collect and unify SIS information with understanding of M365 application interactions. This "usage" data can be combined with other data sources (such as Microsoft Education Teams Insights), to get a real time view of student use of applications. This can also be combined with Graph Reports API Teams/M365 data collection of Microsoft application activities, to produce even richer visualizations and knowledge of which application activities and interactions are deemed as valuable.

Microsoft Insights data can be used for a variety of education purposes, including:
 - School and district dashboards for education leaders to identify variability in student application interactions correlating to grades.
 - Basic school dashboards showing the impacts of attendance based on application use.

Ingesting data using this Microsoft Insights module provides solutions to these scenarios.

## Module Impact
This Microsoft Insights module for OEA will leverage the Azure Synapse environment to aid education systems in bringing this "usage" and SIS data to their own Azure data lake for analysis. This includes a tutorial for extracting digital interaction from Microsoft Teams (if you choose to sign up for the Insights for Teams, shown below) and some M365 apps, providing a more detailed and accurate representation of roster data and the use of Microsoft applications for online learning activities. The PowerBI template included in this module can be used by system and school leaders to show:
 - Students within an education system:
      * Number of students within a school or district
      * Average grades of students within a school or district
      * Demographic breakdown of students within a school or district
 - M365/Teams application use within a education system:
      * Online activities and interactions with Teams by students

This dashboard example represent only data from Microsoft Insights. When this data is combined with other data sources, they can illustrate how attendance patterns can relate to student device use, other forms of online "usage" engagement, etc. With such combined data, education systems can start to analyze whether new programs or interventions help to improve teaching and learning with digital tools.

## Data Sources and Module Setup [STILL IN-PROGRESS]
### Data Sources

- As mentioned before, this Microsoft Insights module utilizes usage data from M365 applications to gauge student interaction and involvement from their online activities. 
     * Note the availability of [Insights in Microsoft Teams for Education](https://support.microsoft.com/en-us/office/insights-preview-in-microsoft-teams-for-education-leaders-8738d1b1-4e1c-49bd-9e8d-b5292474c347?ui=en-us&rs=en-us&ad=us) which provides usage analytics available via the Insights app within Teams. Although, the assets provided within this module focus on the processing of M365 usage data.
 - App usage data available via Azure Data Share:
     * In order to begin receiving usage data from M365, the first step is to initiate the Data Share feature within [School Data Sync](https://sds.microsoft.com/). This feature is in Private Preview and is not visible by default - check with your account manager to have the feature enabled for your tenant.
 - The data ingested is formatted as CSV files.

### Module Setup

 - The setup of [School Data Sync](https://sds.microsoft.com/) is a prerequisite for being able to receive this type of usage data from your M365 tenant.
    * You can also find short videos about School Data Sync and the Insights app on the [Microsoft School Data Sync channel](https://www.youtube.com/channel/UCA8ZOC7eTfzLlkcFW3imkHg/featured).
 - In order to install this module:
     1. Connect your Synpase workspace to the Azure Data Share for M365 data.
     2. Import the MSInsights_py.ipynb and process_MSInsights_data.ipynb notebooks into Synapse Studio.
     3. Then, open and run the process_MSInsights_data notebook.
     4. After the Insights data is processed, open up the PowerBI Insights dashboard template provided, and connect to your Synapse workspace serverless SQL endpoint.
 
## Module Components
Sample out-of-the box assets for this OEA module include: 
1. [Tutorial](https://github.com/cstohlmann/oea-ms_insights-module/tree/main/docs): A tutorial on how to use this module within your own Synapse workspace.
2. [Test data](https://github.com/cstohlmann/oea-ms_insights-module/tree/main/test_data): Ingest sample data to understand the utility and functionality of the notebooks.
3. [Notebook](https://github.com/cstohlmann/oea-ms_insights-module/tree/main/notebook): Example notebooks on processing the data from stage 1 to stage 2 within Synapse. 
4. [PowerBI template](https://github.com/cstohlmann/oea-ms_insights-module/tree/main/powerbi): A Power BI sample template making it easy to interact with Microsoft Insights data.
 <p align="center">
  <strong><em>[INSERT POWERBI DASHBOARD TEMPLATE PICTURE HERE]</em></strong>
 </p>

The Microsoft Insights module [welcomes contributions](https://github.com/microsoft/OpenEduAnalytics/blob/main/CONTRIBUTING.md).

This module was developed by [Kwantum Analytics](https://www.kwantumanalytics.com/). The architecture and reference implementation for all modules is built on [Azure Synapse Analytics](https://azure.microsoft.com/en-us/services/synapse-analytics/) - with [Azure Data Lake Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction) as the storage backbone,  and [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/) providing the role-based access control.

#### Additional Information
| Resource | Description |
| --- | --- |
| [Overview of Microsoft Education Insights](https://docs.microsoft.com/en-us/microsoftteams/class-insights) | Intro to Education Insights, what it can do, and what it can provide. |
| [Syncing SIS Data with Education Insights](https://docs.microsoft.com/en-us/microsoftteams/education-insights-sis-data-sync) | Reference to how to sync SIS data with Education Insights, and includes information on how to integrate SIS data through SDS. |


# Legal Notices
Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
