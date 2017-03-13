# Taking A Look
Jamaal Green  
3/12/2017  


##PUMS

I will be using public-use microdata from the good folks at the [University of Minnesota](https://usa.ipums.org) using the latest five year ACS data. While longitudinal data would be cool this is more of a proof of concept/exploratory look. 

I've chosen 9 variables: birthplace, citizenship status, metropolitan status, city (residence at time of survey), state, employment status, occupation, industry, and income from wages. Most of these variables should be self-explanatory. Of particular importance for this look are clearly birthplace and metropolitan status. This is trying to get at African immigrant employment in non-metro areas. I have the city listed on the off chance I might be able to actually get a reasonable estimate, but I doubt I'll be able to say anything at such a fine geography, but I do have the state in case we do some variation at that scale. 

For the sake of time and not taxing my machine unnecessarily, I pre-filtered the table on the IPUMS site to only those folks who listed an African country as their birthplace and list being employed. This isn't entirely necessary, but it speeds up the processing time on IPUMS end so I can more quickly grab my table. And this will show me straight away if I have a big enough sample to say anything interesting once I get a look at it. 



I'll be making use of the survey package and some cribbed code from [Anthony Damico's](http://www.asdfree.com/search/label/american%20community%20survey%20%28acs%29) indispensable site. Before that, I'll have to filter down my table just a little bit more to isolate African migrants in non-metro areas. 

The final table of African migrants in non-metro areas only has 905 observations. This is an incredible small table and, as such, I can only really speak at the broadest measures, if that. But first let's just see if we can get some reliable basic summary information. Let's start with average wages from income. This is a variable that will give us the income from the jobs an individual works in. 


```
##          mean     SE
## INCWAGE 38279 1729.4
```

Average wages from income for non-metro African migrants is a little less that $40,000 per year. This is a modest but not terrible amount of money and considering many non-metro areas have cheaper housing costs it may be possible to live comfortably on 40k a year absent other major expenses. We know that this is not the case for many immigrant populations, though, who often must pay down personal debts and provide money for back home. 

So, in what industries are these folks working in? In "Global Heartland", the primary employer of immigrants in the study town was a meatpacking plant. It is dangerous, hard work for relatively low pay. As such, it may be reasonable to assume that many of these migrants are working in agricultural processing/manufacturing industries. Such establishments are often hurting for labor, actively recruit African immigrants, and will hire you on the spot. For time sensitive immigrants looking to make as much money as quickly as possible to pay off debt, these jobs are irresistible. So what are these industries?


---------------------------------------------------------------
INDNAICS        Employment    CV                       Industry
------------- ------------ ----- ------------------------------
INDNAICS611M1         2115 1.825 Colleges, Universities & Prof.
                                                        Schools

INDNAICS3116          1569 1.764        Animal Slaughtering and
                                                     Processing

INDNAICS622           1144 1.677                      Hospitals

INDNAICS722Z           963 1.617     Restaurants and Other Food
                                                       Services

INDNAICS6231           631 1.418        Nursing Care Facilities

INDNAICS6111           613 1.401       Elementary and Secondary
                                                        Schools

INDNAICS23             579 1.366                   Construction

INDNAICS92MP           570 1.357     Justice, Public Order, and
                                              Safety Activities

INDNAICS7211           510 1.283          Traveler Accomodation

INDNAICS6216           489 1.253      Home Health Care Services
---------------------------------------------------------------

Table: Top 10 Industries for African Immigrants
 in Non-Metro Areas

As you can see, there's quite a mix of industries here, of both high, medium, and low skilled work. But, also, this mix of industries reflects a rather variegated workforce. 
