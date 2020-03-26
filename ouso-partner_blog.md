# Bartering Data

As fellows, we've learnt a lot already and done a number of [interesting things](http://fellows.frictionlessdata.io/blog/) with Frictionless Data (FD) [tools and specifications](https://frictionlessdata.io/field-guide/). This time around, the goal was to model real-life data interactions; trade each other's data and share on the experience working with them. We barter-traded data packages. Specifically, we aimed to:
>1. understand each other's data, 
2. recreate a data package with the partner's raw data & 
>3. validate the data package with goodtables

My focus was to reproduce Monica's [work](http://fellows.frictionlessdata.io/blog/monica-datapackage-blog/), starting from her [data pacakge](https://github.com/Monsauce/frictionless_data_fellowship/blob/master/firstdatapackage.json) backwards.

## Understanding the data
For any reliable attempt on foreign data, you may agree with me, the best place to begin is the metadata. I understand the structure of a data package `.json` file, thanks to FD fellowship, and so I know that the first place to look at it the area containing the overall metadata of the whole data set. This is usually found at the bottom of the file, that is, if the handler cared to include any metadata. Be like Monica, she provided metadata. The overall metadata directed to the article associated with the data and provided the license, among other things. I found the field metadata to be very informative, for instance, a field label _Day_ could mean a lot of things in and of itself. However, the entries `"title": "Experimental day` and `"description": "Experiment ran for 63 days"`contextualises the heading with clarity.

## Recreating the data package
To do this you, at least, need the data. This was available. Monica had the associated data in GitHub; in a public repository and under a `CC-BY-4.0` license, making it easily `accessible`. To reach the data the I copy-pasted the link, the value of the `path` key, which contains the resource identifier in a web client. The uniform resource identifier (`URI`) makes the data `findable` because it is uniquely associated with only that single item universally. The same link was used inside the [Data Package Creator](http://create.frictionlessdata.io/).  [Here](https://raw.githubusercontent.com/ousodaniel/FrictionlessDataFellowship/master/datapackage_MonS.json) is the package I recreated.

## Validate the data package
On validating the data package I came across two warnings regarding row limits for the _Algae.csv_ and _Tiles.csv_ tables. There was one `type format` error for the `Density` field in the Algae data set. The error was occasioned by having the `type` as `integer` rather than `number`, as the field contain floats. On [rectifying](https://raw.githubusercontent.com/ousodaniel/FrictionlessDataFellowship/master/datapackage_MonS_Ouso.json) this in the data package I recreated the `type error` disappeared. I raised an [issue](https://github.com/Monsauce/frictionless_data_fellowship/issues/3) with the solution on GitHub. The `CSV` and the `JSON` data formats allowed for `interoperability` given we, Monica and I, work on different software and hardware platforms.

## Conclusion
Exchanging data packages and working backwards from them is an important test in the illustration of the overall goal of the Frictionless Data initiative. Remember, FD seeks to facilitate and promote open and reproducible research, consequently promoting collaboration. By trying to reproduce Monica's work I was able to capture an error, which I highlighted for her attention, thus improved the work. Exactly how science is supposed to work!


