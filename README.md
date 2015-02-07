
# Volunteer Job Openings REST API
#### Version 1.0

http://www.peacecorps.gov/api/v1/openings/

## Peace Corps Volunteer Job Openings Dataset

Peace Corps service is a personal and professional experience like no other. Volunteers live and work abroad for two years sharing their skills and working to make a difference in their communities. There are a wide variety of Volunteer openings in more than 60 countries that have asked for assistance. The dataset this API exposes is all current Peace Corps Volunteer Job Openings. An interactive list of volunteer job openings can be found on the Peace Corps website here.

Peace Corps has an Openings browser that can be found here: http://www.peacecorps.gov/openings/search/

## Volunteer Job Openings API

The Peace Corps Volunteer Job Openings REST API provides read-only access and currently supports JSON data format. The API uses pagination to limit the number of records that appear at one time. Individual users (per IP) are limited to 15 requests per second. Developers, designers, engineers, and partners are all encouraged to leverage the Volunteer Job Openings API to build innovative tools and/or creatively share data.


## Volunteer Job Openings API Elements

Name	| Type |	Description
----|----|----
title	| String |	Job opening title.
req_id	| String	| Unique job opening identifier.
country	| String	| Country the job opening is in. (slug) 
region	| String	| Region the job opening is in. (slug) 
sector	| String	| Job sector.
appy_date	| Date	| Apply by date.
know_by	| Date	| Know by date.
staging_start_date	| Date	| Depart by date.
featured	| Boolean	| Featured job opening.
project_description |	Text	| Job description.
required_skills	| Text	| Required skills.
desired_skills	| Text	| Desired skills.
language_skills	| String	| Language skills.
language_skills_comments	| Text	| Language skills comments.
volunteers_requested	| Number	| Positions available.
accepts_couples	| Boolean	| Job opening accepts couples.
living_conditions_comments	| Text	| Living conditions.
country_medical_considerations	| Text	| Country medical considerations.
country_site_url	| String	| Country site URL.
country_flag_image	| String	| Country flag image URL.
opening_url	| String	| Job opening URL on Peace Corps website.


## Resources

- GET /api/v1/openings
- GET /api/v1/openings/{req_id}

	
## GET /api/v1/openings

Returns a list of all Peace Corps volunteer job openings. You can filter the results by using the following query parameters/arguments in the URL:

### Arguments

Argument |	Description	| Keyword
----|----|----
country	| Filter by country/countries. (e.g. ?country=ethiopia) Note: You may filter by multiple countries. The following arguments in the URL will return all Ethiopia and Philippines job openings if any. ?country=ethiopia&country=philippines	| Use country slug.
region	| Filter by region/s.(e.g. ?region=africa) Note: You may filter by multiple regions. The following arguments in the URL will return all job openings within the Eastern European region and African region. ?region=easteurope&region=africa	| Use region slug.
sector	| Filter by sector/s. (e.g. ?sector=health) Note: You may filter by multiple sectors. The following arguments in the URL will return all job opening within the ‘health’ sector and ‘education’ sector. ?sector=health&sector=education	| Use the following keywords for the six Peace Corps sectors: agriculture, community economic development, education, environment, health, youth in development
language	| Filter by language/s. (e.g. ?langauge=spanish) Note: You may filter by multiple languages. The following arguments in the URL will return all job openings with either a Spanish or French requirement. ?langauge=spanish&language=french. Use the following keywords for language requirements: french, spanish, romance (any romance language), russian, other, none (no language requirement)
keyword	| Filter by keyword. (e.g. ?keyword=malaria) Note: You may NOT filter by multiple keyword arguments, however you may search for multiple consecutive words using one keyword argument in the URL. The following argument in the URL will return all job openings with the words “malaria prevention.” (e.g. ?keyword=malaria prevention) The following fields are keyword searchable: country, region, sector, title, project description, desired skills, required skills, language skills comments, living conditions comments. | Any keyword.
featured	| Filter by featured job openings. (e.g. ?featured=true) | Use ‘true’ or ‘false’
couples	| Filter by couples accepted. (e.g. ?couples=true) | Use ‘true’ or ‘false’

## Request Example

http://www.peacecorps.gov /api/v1/openings/?country=cambodia&keyword=teacher

#### Response Example

> {
count: 2,
next: null,
previous: null,
results: [
{
title: "English Teaching and Teacher Trainer",
req_id: "2929br",
country: "cambodia",
region: "asia",
sector: "Education",
apply_date: "2015-01-15",
know_date: "2015-03-15",
staging_start_date: "2015-06-29",
featured: true,
project_description: "This assignment requires Volunteers to teach English to students at basic to intermediate levels, including mixed ability at the secondary level (7th, 8th, 9th, 10th, 11th and 12th grade). In addition, Volunteers will also lead extracurricular activities to enrich learning opportunities for their students. All classes are co-taught with a Cambodian counterpart. Candidates will teach in either secondary school or teacher trainer centers.",
required_skills: "Volunteers work with new and experienced teachers to teach English in secondary schools and teacher training centers. Volunteers share current methodologies, subject content and develop resources, creating sustainable improvements in teaching that will affect generations of future students. Projects include increasing local teachers’ English language competency and conversational skills, organizing training seminars and becoming involved in community and school based projects.",
desired_skills: "All Candidates are required to have a MAT (Master's in Teaching) in English, TEFL, foreign language or Applied Linguistics; OR MEd with graduate or undergraduate concentration in English, TEFL or foreign language; OR BA/BS in Secondary Education with concentration in English, TEFL or foreign language; OR BA/BS in any discipline with secondary education state certification in English, TEFL or foreign language; OR BA/BS in English, TEFL or foreign language with 6 months, classroom teaching experience at the secondary level in English, TEFL or foreign language; OR BA/BS in any discipline with 1 year classroom teaching experience at the secondary level in English, TEFL or foreign language. The ability to ride a bike is required as Volunteers' primary mode of transportation in Cambodia is a Peace Corps provided bicycle. Volunteers should be comfortable riding a bicycle for short to moderate distances (1-5 miles per day).",
language_skills: "none",
volunteers_requested: 7,
accepts_couples: true,
living_conditions_comments: "All Volunteers (including couples) live with host families for the duration of their service. Families live communally often with several generations sharing one home. While Volunteers will have their own room in the home, they are typically afforded less privacy than they are accustomed to. Volunteers are required to live according to local cultural norms, which include sharing at least one meal with the host family each day and participating in family events. During PST married couples who are serving in different projects (English and Health) will not live together. They will be able to see each other approximately once per week and will have phones with which they can communicate each day. Candidates should note that they will often be working in extreme heat and humidity. Most often, this assignment will place a Volunteer in a rural location where transportation options may be limited. However, a few assignments are in provincial towns. Some Volunteer sites are a days travel from the Peace Corps office in Phnom Penh and may be several hours from another Peace Corps Volunteer. Some sites do not have regular access to electricity or internet service. Cultural sensitivity is equally essential including an awareness of the recent genocide and the effect it continues to have on the population. The effect of the genocide reaches every corner of life in Cambodia. Everyone over the age of 40 remembers the genocide firsthand. Cambodians are largely unaware of American diversity and are often curious about minority Volunteers’ nationalities. Minority Volunteers should be prepared to answer a large number of questions on this topic.",
country_medical_considerations: "",
country_site_url: "http://cambodia.peacecorps.gov",
country_flag_image: "",
opening_url: "http://www.peacecorps.gov/openings/2929br/"
},
{
title: "English Teaching and Teacher Trainer",
req_id: "2930br",
country: "cambodia",
region: "asia",
sector: "Education",
apply_date: "2015-01-15",
know_date: "2015-03-15",
staging_start_date: "2015-06-29",
featured: false,
project_description: "This assignment requires Volunteers to teach English to students at basic to intermediate levels, including mixed ability at the secondary level (7th, 8th, 9th, 10th, 11th and 12th grade). In addition, Volunteers also lead extracurricular activities to enrich learning opportunities for their students. All classes are co-taught with a Cambodian counterpart. Candidates will teach in either secondary school or teacher trainer centers.",
required_skills: "All candidates are required to have a four year degree in Secondary Education with concentration in English, TEFL or a foreign language; OR BA/BS in any discipline with state certification at the secondary level in any discipline (English, TEFL, foreign language, art, or social science); OR BA/BS in English, TEFL or Linguistics; OR BA/BS in any discipline with 3 months, 10 hours/month, or 30 hours of English, foreign language, or literacy tutoring experience with primary school, middle or high school students, or adults. Candidates might also have a MAT (Master's in Teaching) in English, TEFL, foreign language or Applied Linguistics; OR MEd with graduate or undergraduate concentration in English, TEFL or foreign language; OR BA/BS in Secondary Education with concentration in English, TEFL or foreign language; OR BA/BS in any discipline with secondary education state certification in English, TEFL or foreign language; OR BA/BS in English, TEFL or foreign language with 6 months, classroom teaching experience at the secondary level in English, TEFL or foreign language; OR BA/BS in any discipline with 1 year classroom teaching experience at the secondary level in English, TEFL or foreign language.",
desired_skills: "The ability to ride a bike is required as Volunteers' primary mode of transportation in Cambodia is a Peace Corps provided bicycle. Volunteers should be comfortable riding a bicycle for short to moderate distances (1-5 miles per day).",
language_skills: "none",
volunteers_requested: 33,
accepts_couples: true,
living_conditions_comments: "All Volunteers (including couples) live with host families for the duration of their service. Families live communally often with several generations sharing one home. While Volunteers will have their own room in the home, they are typically afforded less privacy than they are accustomed. Volunteers are required to live according to local cultural norms, which include sharing at least one meal with the host family each day and participating in family events. During PST married couples who are serving in different projects (English and Health) will not live together. They will be able to see each other approximately once per week and will have phones with which they can communicate each day. Candidates should note that they will often be working in extreme heat and humidity. Most often, this assignment will place a Volunteer in a rural location where transportation options may be limited. However, a few assignments are in provincial towns. Some Volunteer sites are a days travel from the Peace Corps office in Phnom Penh and may be several hours from another Peace Corps Volunteer. Some sites do not have regular access to electricity or internet service. Cultural sensitivity is equally essential including an awareness of the recent genocide and the effect it continues to have on the population. The effect of the genocide reaches every corner of life in Cambodia. Everyone over the age of 40 remembers the genocide firsthand. Cambodians are largely unaware of American diversity and are often curious about minority Volunteers’ nationalities. Minority Volunteers should be prepared to answer a large number of questions on this topic.",
country_medical_considerations: "",
country_site_url: "http://cambodia.peacecorps.gov",
country_flag_image: "",
opening_url: "http://www.peacecorps.gov/openings/2930br/"
}
]
}

## GET /api/v1/openings/{req_id}

Returns a single volunteer job opening according to what ID is added to the URL. 

## Request Example

http://www.peacecorps.gov/api/v1/openings/3164br/

#### Response Example
> {
title: "Healthy Schools Coordinator",
req_id: "3164br",
country: "guatemala",
region: "centralamerica",
sector: "Health",
apply_date: "2015-01-15",
know_date: "2015-03-15",
staging_start_date: "2015-09-22",
featured: false,
project_description: "Healthy Schools Volunteers will work to support national government efforts to strengthen the Guatemala Healthy Schools Project. The purpose of the project is to improve the health status of rural students (grades K-6) through the sustainable and systematic practices of healthy habits. Your goal will be to coordinate and support the implementation of the Healthy Schools project in participating schools. And in order to achieve this goal you will be working to accomplish the following objectives: 1. Train school principals and teachers in the overall management of the Healthy Schools project, including specific technical areas such as basic hygiene, nutrition, sex education, peer education, and trash management. A fundamental component of this task includes the training of trainers, especially in the development of more effective and creative lesson plans. 2. Provide technical support (including the process to solicit funds) in order to improve sanitation infrastructure, including rain catchment systems, latrines and multifaucet stations. 3. Encourage monitoring and evaluation by providing feedback and support to school principals and teachers regarding project progress. 4. Work with staff, school committees, community leaders and parents to promote the sustainability of the Healthy Schools project. The community needs to view the project as a priority, to care for it as much as you do … this in itself will be a two year process. 5. Coordinate your work with your district superintendent and other key players such as health centers/posts and local NGOs.",
required_skills: "Competitive candidates will meet or exceed the following criteria: Demonstrated ability in planning, organizing, counseling on leadership within the past 5 years, AND one of the following: • BA/BS in Social Work, Social Services, Counseling or Community Development; OR • BA/BS in any discipline with relevant volunteer experience.",
desired_skills: "You should have experience and/or interest in school and community-based health promotion.
language_skills: "spanish",
volunteers_requested: 14,
accepts_couples: true,
living_conditions_comments: "Guatemala is a traditional society, and the social, work, and gender roles of women, men, elders, and youth are much more clearly defined than in the U.S. Volunteers should learn and be respectful of their practices, customs, and way of life. Professional dress is expected in Peace Corps/Guatemala. Clothing in the field can sometimes be casual but should still be professional. You will note that rural people wear plain clothes when they are working, but they wear their best attire when visiting government agencies, attending a meeting, or party. For the trainees/Volunteers this can mean nice slacks, collared shirt, closed-toe shoes for men and skirt and blouse for women. Volunteers in Guatemala have homestay with a host family during the 10-week Pre-Service training and during the 2 years of service. Volunteer sites have a wide variety of climates and living conditions. Most Volunteers are placed in the Western Highlands of Guatemala which is quite mountainous and…",
country_medical_considerations: "",
country_site_url: "http://guatemala.peacecorps.gov",
country_flag_image: "",
opening_url: "http://www.peacecorps.gov/openings/3164br/"
}




## Pagination

By default, the API paginates the results with 25 results per page. The “next” field within the JSON results contains the URL to the next page if there is one, while the “previous” field contains the URL to the previous page if there is one. 

If you want to display more than 25 records per page, you have the option to override the page size using the “page_size” parameter.
(e.g. http:/www.peacecorps.gov/api/v1/openings/?page_size=50 ). 
The maximum page size is 100. 
