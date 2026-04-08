# Longitudinal Analysis of the Allegheny County Jail Oversight Board Meeting Minutes

The following writeup comes from our project proposal submitted on April 3, 2026 for the course *Unstructured Data Analytics*.

**Contributors:** Samiha Islam, Afifa Iqbal, Anna Ringwood, Danielle Aira Savellano, Matteo Secomandi

## Background

The [Allegheny County Jail Oversight Board](https://alleghenycontroller.com/the-controller/jail-oversight-board/) (JOB) is a statutory entity responsible for (1) maintaining the county jail and other facilities, (2) overseeing the well-being and safety of incarcerated persons, and (3) confirming wardens selected by the County Executive. The Allegheny County Jail (ACJ) has received [criticism](https://abolitionistlawcenter.org/allegheny-county-jail/) for its treatment of those incarcerated (particularly those who have disabilities and mental and physical health needs), poor living conditions, and staff misconduct. At least [thirteen people](https://penncapital-star.com/criminal-justice/thirteen-men-died-after-going-to-the-allegheny-county-jail-here-are-their-stories/) have died in the jail since the onset of COVID-19, and this number is likely an underestimate. Several [lawsuits](https://abolitionistlawcenter.org/allegheny-county-jail/#:~:text=its%20feeder%20institutions.-,Litigation,-Howard%20v.%20Williams) are also underway against ACJ for deaths of incarcerated people, among other infractions.

In 2021, a countywide voter referendum banning the use of solitary confinement in the ACJ passed with [nearly 70% support](https://ballotpedia.org/Allegheny_County,_Pennsylvania,_Prohibit_Solitary_Confinement_Initiative_(May_2021)). However, the county has maintained the use of “pod lockdowns” and “segregated housing,” which activists describe as [replicating solitary confinement conditions](https://www.wesa.fm/courts-justice/2024-07-09/allegheny-county-jail-reduces-solitary-confinement-but-advocates-say-more-must-be-done). Former ACJ Warden Orlando Harper was [heavily condemned](https://www.post-gazette.com/local/city/2023/09/07/retiring-allegheny-county-jail-warden-orlando-harper/stories/202309070140) during public comments shared at JOB meetings for creating a “toxic” and “militaristic” environment within the jail. He was succeeded by Warden Trevor Wingard in 2025, who joined ACJ with a mission of improving jail conditions. He has been [praised](https://community.triblive.com/news/3807776) in recent interviews with legal observers, and has notably [fired](https://www.cbsnews.com/pittsburgh/news/allegheny-county-jail-racist-video/) a controversial corrections officer after investigating frequent criticism shared by inmates.

Given the JOB’s responsibility for conditions at ACJ, one would expect that meetings include discussion of topics like health care, food, and staff behavior. 

## Policy Questions

- Which topics are more frequently discussed at meetings?
    - What types of solitary confinement policies are in use in ACJ and how has this changed over time? 
        - This might be identified through keyword searches for the different types of confinement (“solitary confinement,” “pods,” “segregated housing”) and seeing which ones occur most frequently each year 
- How have discussion topics at meetings changed over time?
- Can evidence of improvement (or lack thereof) in conditions or staff behavior be derived from the minutes?
    - E.g., evidence of harm in jails can be measured through text searches for violent incidents (“punched”, “tased”, “choked”, “attacked”)
    - Evidence of improvement could be measured through text searches for corrective actions and policies (“fired,” “banned,” “resolved”)
- Do common topics from meeting minutes align with those from public comments? In other words, is the JOB discussing topics of concern from county residents?
    - One specific topic we could focus on: Is the ACJ JOB aware of public outrage over solitary confinement and prison condition complaints? To what extent is it being discussed in JOB meetings?
- Are certain correctional officers, sergeants or staffers associated with being particularly helpful or harmful to the wellbeing of the inmates? 
- Has the discussion (and by implication, the frequency) of crises and violent incidents in ACJ changed between the administration of Warden Harper and current Warden Wingard?

## Datasets

Analysis will focus on the official Allegheny County JOB Meeting Minutes. These documents serve as the formal record of the board’s deliberations, public interactions, and administrative decisions. These JOB meetings typically occur monthly, are open to the public, and are livestreamed and recorded on the JOB YouTube channel. As an essential part of each meeting, the public is permitted to submit comments online via the County Courts website or sign up for in-person public comment before the session begins.

The data is fundamentally unstructured because it consists of PDF files containing free-form text transcripts. Unlike a structured database, these records include a raw mix of procedural motions, warden reports, and verbatim public testimony. While the documents contain a built-in word index that tracks terms like “health,” “force,” and “respect,” the actual content of the meetings remains in a narrative format that requires extraction to identify patterns.

These minutes can be accessed on the Jail Oversight Board website, under the “[Meeting Minutes](https://alleghenycontroller.com/the-controller/jail-oversight-board/jail-oversight-board-internal/)” section. The collection of meeting minutes spans over 13 years of records, including minutes from March 2012 through April 2026.

## Methodology

The analysis can be broken down into four phases:

- **Text Preprocessing.** PDF meeting minutes will be downloaded directly from the JOB website and converted into text in preparation for computational analysis. A potential obstacle at this stage would be the varying formatting styles over the 13-year period. Preprocessing will also focus on tokenization, removal of stop words, and lemmatization.
- **N-Gram Frequency Analysis.** Frequent terms and N-grams will be identified to describe the board’s discourse. Recurring themes essential to jail oversight will be highlighted. These could potentially include concepts like “use force,” “mental health,” “solitary confinement,” “women’s health,” etc.
- **Topic Modeling.** Discussion points will be categorized into thematic clusters. Theme prevalence will also be tracked over the 13-year timeline to understand how the board’s and public’s priorities have evolved or shifted over time.
- **Sentiment Analysis.** The emotional tone of both the board discussion and public comment could also be evaluated. By comparing this to the official actions or motions in the meeting minutes, we may be able to assess the board's responsiveness in relation to public commentary.

## Expected Findings

We expect to observe significant shifts in the topics and tone reflected in the JOB meeting minutes over the thirteen year span of the data. The history of incarceration in the US is heavily intertwined with that of slavery and racism and has thus always been a hotly debated policy area with periods of perspectives shifting towards both harsher punishment and liberalization. 

The most recent trend has been towards criminal justice reform evidenced by the US prison population’s [steady decline since its 2009 peak](https://www.vera.org/news/jail-and-prison-populations-have-decreased-since-2019-but-continued-progress-isnt-promised#:~:text=Researchers%20generally%20consider%202009%20to,close%20behind%20at%203.6%20percent.). Thus, we expect to see discussions on mental health, recidivism, racial discrimination, and other similar topics become more prevalent since the beginning of the data. Given that the meetings are able to be attended by members of the public, we expect to also see a more fragmented trend in activist participation.

Although we expect to find a long-term trend of increased frequency of criminal justice reform related topics, we also anticipate that changes in board membership and prison leadership will lead to identifiable deviations as well. These shifts in sentiment are likely to be stronger when the position of Warden changes as they have the greatest influence over policies that would merit JOB attention.