---
title: "Alpha"
section: "Brownfield sites"
label: "project:brownfield-sites"
pageFeedback: true
summary: We’re exploring digital tools that could help local planning authorities collect and maintain brownfield site data.
layout: single
---

### A national index of brownfield land data

#### Question we asked

Brownfield land data can be difficult to locate and there’s no single public register where all local planning authorities’ data can be viewed. Would a national index of all brownfield data be of value to local planning authorities and interested members of the community?

#### What we tested

* a simple [index of brownfield land registers](https://github.com/digital-land/brownfield-land-collection/blob/master/dataset/brownfield-land.csv)

>picture

#### What we learned

We made a number of useful observations while building this index, including that:

* local planning authorities often do not provide a direct link to the data (for example, we found links to a policy page instead of to a CSV file)
* when some registers were updated the URL changed, meaning the link is not persistent
* registers were often published in formats other than CSV, such as Microsoft Excel
* registers often contained gaps or errors in the data

### Guidance on updating your brownfield site data

#### Question we asked

Would clearer and simpler guidance help local authorities publish their brownfield data to a standard format and minimise errors and gaps in the data?

#### What we tested

We rewrote the old brownfield register data standard to make it shorter, simpler and easier to use. We tested our new guidance format in the lab with local planning authorities and iterated the content based on our findings.

View the most [up-to-date guidance (beta)](https://www.gov.uk/government/publications/brownfield-land-registers-data-standard/publish-your-brownfield-land-data).

#### What we learned

The new guidance is easier to follow, yet there is some reluctance to follow the format and regularly publish data. There is also confusion around many fields and headers which leads to errors or gaps in the data. Making the guidance even more clear and simple should help this.

Some people want as little content as possible, so that the task of publishing their data can be completed quickly. However, other people want to know the motivation and reasons for having or deprecating certain fields, or reasons for formatting data in certain ways. We think that linking from the guidance on GOV.UK to our data principles will be a good way for those interested in our reasoning and motivation behind data standard decisions to learn more.

### Brownfield site data validator

#### Question we asked

Would offering a digital tool for validating a local authorities’ data improve the accuracy of the data?

#### What we tested

We built and tested a general data validator then, building on our learnings, designed a new tool tailored to [checking brownfield land data](https://brownfield-sites-status.herokuapp.com/). This validator will check local planning authorities' brownfield site data and display the [results of all local authorities' data](https://brownfield-sites-status.herokuapp.com/breakdown).

View the most [up-to-date validator (beta)](https://brownfield-sites-validator.herokuapp.com/).

#### What we learned

We benchmarked against existing data validators, most of which display errors in one long stream. After designing our first prototype based on this model, showing all errors to the user at once, we found this design to be overwhelming.

Many users may not have the technical skills to fix all types of errors, such as changing Microsoft Excel settings so that it doesn’t automatically reformat dates.

Also, some files contain a huge amount of errors. Sometimes, if one column is formatted incorrectly, the validator would list as many errors as there were entries under that single header, despite this is only one type of error.

We iterated our prototype to group errors by type, such as by headers. This way, the validator does not show the user a long list of all errors, but categorises errors and allows the user to expand each error type to view a full breakdown.

### A way of fixing errors

#### Question we asked

Many of the errors we identified in published brownfield data were common mistakes, such as switching GeoX and GeoY coordinates, or date formatting. Therefore, would offering to automatically fix common errors after validating the data be useful and improve the state of data?

#### What we tested

* a [validation tool](https://brownfield-sites-status.herokuapp.com/) for brownfield land data

View the most [up-to-date validator (beta)](https://brownfield-sites-validator.herokuapp.com/) into which we have built several automated fixes.

#### What we've learned

We spoke with people from local planning authorities who are responsible for publishing data. Often they were not technically trained or experienced with working with data. We tested an initial prototype of the validator with some of these users, many of whom were able to spot and correct the data errors. We may work on building a way to automatically correct errors into the new validator.

!! If you have any questions or feedback, please email <DigitalLand@communities.gov.uk>
