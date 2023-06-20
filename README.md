# Actor - Apartment List Scraper

## Apartment List scraper

ApartmentList.com is a popular online platform that connects renters with apartments across the United States. It offers a wide range of rental listings, helping individuals find their ideal living space based on their preferences and requirements. From spacious studios to luxurious penthouses, ApartmentList.com features listings from various property owners and management companies.

With its extensive database, ApartmentList.com provides detailed information about each apartment, including rental prices, amenities, location, and more. However, accessing this data programmatically can be challenging, as the platform does not offer a dedicated API for developers to retrieve information efficiently.

That's where our ApartmentList.com scraper comes in. This powerful tool is designed to extract data from ApartmentList.com, enabling you to gather the information you need for your specific purposes. Whether you're a real estate professional, a researcher, or someone searching for an apartment, this scraper simplifies the process of accessing and organizing the apartment listings from ApartmentList.com.

The Apartment List data scraper supports the following features:

-   Scrape lists - Scrape any list that you'd like to get from Apartments List

-   Scrape property details - Scrape a very detailed information for each of the property that you'd like to get.

## Bugs, fixes, updates and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/apartmentlist-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on Apartment List that should be visited. Required fields are:

- `startUrls`: (Optional) (Array) List of Apartment List URLs. You should only provide news list, jobs list or detail URLs.

- `endPage`: (Optional) (Number) Final number of page that you want to scrape. Default is `Infinite`. This is applies to all `search` request and `startUrls` individually.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as argument and returns object with data.

- `customMapFunction`: (Optional) (String) Function that takes each objects handle as argument and returns object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

When you want to have a scrape over a specific list URL, just copy and paste the link as one of the **startUrl**.

If you would like to scrape only the first page of a list then put the link for the page and have the `endPage` as 1.

With the last approach that explained above you can also fetch any interval of pages. If you provide the 5th page of a list and define the `endPage` parameter as 6 then you'll have the 5th and 6th pages only.

### Compute Unit Consumption

The actor optimized to run blazing fast and scrape as many items as possible. Therefore, it forefronts all the detail requests. If actor doesn't block very often it'll scrape 100 listings in 4 minutes with ~0.01-0.03 compute units.

### Apartment List Scraper Input example

```json
{
  "startUrls": [
    "https://www.apartmentlist.com/co/denver"
  ],
  "proxy": {
    "useApifyProxy": true
  },
  "endPage": 5,
  "maxItems": 20
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with failure state and output an explanation of what is wrong.

## Apartment List Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any languague (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Apartment List actor.

## Scraped Apartment List Properties

The structure of each item in Apartment List looks like this:

### Property Detail

```json
{
  "url": "https://www.apartmentlist.com/co/denver/zia-sunnyside",
  "type": "Property",
  "photos": [
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/3366a2ab65c44b698cdc59313fd80c65.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/3b913b788940e3b75240d394402b773a.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/633b39d601c3da70e595d153d6cfd1d9.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/6d72f699f51db2dbb9375b5c6ee463dc.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/aa5f03b5012ce89ebb42ee00cc425f0d.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/7a2b4f1a98f869eb2191e9be5734034d.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/e0463c236069d1a6bb4501f3da0a1a87.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/1dfc17f52f35099934b348479a319205.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/9d982e406bbd2c48c936254d585bf9b6.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/f927e853a46bbed00ae370eebd534eec.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/01bc696248f0aba4842dd0e4030a65f6.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/419725ccbcee9845157d1cc52f7608af.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/cf45cc4dd15830f91b4af9e735a5e4c4.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/539c4fd2aeed6eb4ea367debd7147efe.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/f8da18d6bab29d21b47a147b6a970dab.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/f9f1ccc7b121dd4b06c6b2c60489da1f.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/9b9fec2e5cec24177f81f1c7b95dd4a8.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/b8a1ffa08359f3aa79dd1493bf0f078b.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/a6c5874038819246844384df6735e56c.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/7b920d1220556698041fa1e529532d92.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/a2bcf9859558c27daff79477383f8a28.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/08ccc8640beaad69279e988b2494c312.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/dc5040aaf64b00582ece10694a689d68.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/18e4153787234ba01020dd59fceff4ee.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/4c76022fc8d7764fcf1033cc4d6f6e6b.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/9f3cd004a578d1fe1f04778b7f0c3821.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/20105cbc8daffae866bd67f0c9f79052.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/e0c42d4161e2de6756b78c53d08e41e8.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/746433859cc98b0374848f1ae3d317ca.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/59654d48293640625f31a7ddea016421.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/b9b2ee7a70cd602cb98ec6aff18aff77.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/1f20e50e9b3d3c6f18a782e9fabcccec.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/76ac7fe125cc1627bddb93e4db400ff8.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/40f1de20c896345215905be7dd7a7de3.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/1f481e4d83e0923b53b7cd704cf8c30e.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/935c2634af9319d944ae5dd355cf78ca.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/ab10c7838858af8622b08767d258eb45.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/bfff57ba2705574961cdf17d7d76ec9f.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/2a945b951951f70e87a752ecfa45fe50.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/e18414fde189dd49f077c3ee4b8e81bb.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/2dce7e854dc38704105ac095a9d4a32d.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/66378c423d523ae97c8b8e1570509706.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/1d4afe832b352a5909162948275c1578.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/f62994210964eb3b2538f8efcbd5db0d.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/3ec19ba57c2e0e9120a9c2819846102c.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/6c29a254c1e4da9d8b01320476d69241.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/a05a059dcfd0c2897178ad357413750e.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/3c4fe810869e96a4954fc0f87cf1d65d.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/23ca70c38429b31a429556d292e97022.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/2cf7a54c24184b9d53f071252eab3c7b.jpg",
    "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/af99c72f93a4574d9408b657895df12c.jpg"
  ],
  "scrapedAt": "2023-06-20T22:35:51.036Z",
  "updatedAt": "2023-06-20T22:34:09.698Z",
  "coordinates": {
    "latitude": 39.772577,
    "longitude": -104.9984979
  },
  "propertyName": "Zia Sunnyside",
  "description": "Where being home can feel like being on vacation. Zia Sunnyside is an urban dweller's paradise. From co-working spaces to a spa, from fitness classes to a firepit. Everything you need right outside your front door. Conveniently located steps from the 41st & Fox commuter rail station, residents will be one stop away from Union Staion and all of Denver. At Zia Sunnyside, life is brighter!",
  "depositFee": "No deposit required with approved credit.",
  "isActive": true,
  "additionalFees": "$10 Pest Control; $15 Trash Removal; $50 Basic Internet",
  "applicationFee": "$19.45 per applicant",
  "isAdvertisable": true,
  "leaseTerms": "6-15 months",
  "moveInFees": null,
  "parkingDetails": null,
  "id": "p37540959",
  "rentalType": "apartment",
  "storageDetails": null,
  "availabilityLastChecked": "2023-06-20T22:22:18.176Z",
  "location": {
    "fullAddress": "4055 Inca Street, Denver, CO 80211",
    "state": "CO",
    "city": "Denver",
    "postalCode": "80211",
    "streedAddress": "4055 Inca Street"
  },
  "amenities": [
    "Dogs allowed",
    "Pet friendly",
    "Clubhouse",
    "Courtyard",
    "Elevator",
    "Fire pit",
    "24hr gym",
    "Green community",
    "Parking",
    "Pool",
    "Bbq/grill",
    "Bike storage",
    "Garage",
    "Guest suite",
    "Hot tub",
    "Package receiving",
    "Cats allowed",
    "Accessible",
    "24hr maintenance",
    "Business center",
    "Car charging",
    "CC payments",
    "Conference room",
    "E-payments",
    "Game room",
    "Guest parking",
    "Internet cafe",
    "Key fob access",
    "Lobby",
    "Media room",
    "Online portal",
    "Smoke-free community",
    "Trash valet",
    "Yoga",
    "Air conditioning",
    "Carpet",
    "Dishwasher",
    "Extra storage",
    "Garbage disposal",
    "In unit laundry",
    "Microwave",
    "Patio / balcony",
    "Refrigerator",
    "Stainless steel",
    "Furnished",
    "Hardwood floors",
    "Bathtub",
    "Ice maker",
    "Oven",
    "Range",
    "Smoke-free units",
    "Walk in closets"
  ],
  "schools": [
    {
      "type": "public",
      "name": "Trevista Ece-8 At Horace Mann",
      "grades": "PK-5",
      "numberOfStudents": 351,
      "rating": "3/10",
      "distance": 0.261754974268955
    },
    {
      "type": "public",
      "name": "Bryant Webster K-8 School",
      "grades": "PK-8",
      "numberOfStudents": 425,
      "rating": "5/10",
      "distance": 0.6358336137360657
    },
    {
      "type": "public",
      "name": "Garden Place Elementary School",
      "grades": "PK-6",
      "numberOfStudents": 376,
      "rating": "5/10",
      "distance": 0.7194944774565972
    },
    {
      "type": "charter",
      "name": "STRIVE Prep - Sunnyside Campus",
      "grades": "6-8",
      "numberOfStudents": 264,
      "rating": "3/10",
      "distance": 0.7958826199560068
    },
    {
      "type": "public",
      "name": "Academia Ana Marie Sandoval",
      "grades": "PK-6",
      "numberOfStudents": 420,
      "rating": "5/10",
      "distance": 0.9512246862254092
    },
    {
      "type": "public",
      "name": "Columbian Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 268,
      "rating": "2/10",
      "distance": 1.3284801057141438
    },
    {
      "type": "charter",
      "name": "University Preparatory School",
      "grades": "K-5",
      "numberOfStudents": 346,
      "rating": "6/10",
      "distance": 1.3351755417189657
    },
    {
      "type": "charter",
      "name": "Academy Of Urban Learning",
      "grades": "9-12",
      "numberOfStudents": 108,
      "rating": "1/10",
      "distance": 1.3716209207004113
    },
    {
      "type": "public",
      "name": "Beach Court Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 263,
      "rating": "4/10",
      "distance": 1.392346653000609
    },
    {
      "type": "public",
      "name": "Valdez Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 406,
      "rating": "6/10",
      "distance": 1.404318796357513
    },
    {
      "type": "charter",
      "name": "Strive Prep - Excel",
      "grades": "9-12",
      "numberOfStudents": 317,
      "rating": "4/10",
      "distance": 1.5173125059713921
    },
    {
      "type": "public",
      "name": "North High School",
      "grades": "9-12",
      "numberOfStudents": 1115,
      "rating": "3/10",
      "distance": 1.5173125059713921
    },
    {
      "type": "charter",
      "name": "Wyatt Academy",
      "grades": "K-5",
      "numberOfStudents": 260,
      "rating": "7/10",
      "distance": 1.6711236558837785
    },
    {
      "type": "charter",
      "name": "Dsst: Cole High School",
      "grades": "9-12",
      "numberOfStudents": 397,
      "rating": "5/10",
      "distance": 1.6963235744155991
    },
    {
      "type": "public",
      "name": "Cole Arts And Science Academy",
      "grades": "PK-5",
      "numberOfStudents": 477,
      "rating": "2/10",
      "distance": 1.6963235744155991
    },
    {
      "type": "public",
      "name": "Fred N Thomas Career Education Center",
      "grades": "9-12",
      "numberOfStudents": 472,
      "rating": "4/10",
      "distance": 1.7339383194787927
    },
    {
      "type": "public",
      "name": "Skinner Middle School",
      "grades": "6-8",
      "numberOfStudents": 608,
      "rating": "6/10",
      "distance": 1.7494654318851206
    },
    {
      "type": "charter",
      "name": "The Boys School Of Denver",
      "grades": "6",
      "numberOfStudents": 87,
      "rating": "4/10",
      "distance": 1.776143431630358
    },
    {
      "type": "public",
      "name": "Polaris at Ebert Elementary School",
      "grades": "1-5",
      "numberOfStudents": 334,
      "rating": "9/10",
      "distance": 1.7947729056942598
    },
    {
      "type": "public",
      "name": "Whittier K-8 School",
      "grades": "PK-8",
      "numberOfStudents": 288,
      "rating": "4/10",
      "distance": 1.9270033921856167
    },
    {
      "type": "public",
      "name": "Manual High School",
      "grades": "9-12",
      "numberOfStudents": 309,
      "rating": "2/10",
      "distance": 1.968919592466477
    },
    {
      "type": "charter",
      "name": "Downtown Denver Expeditionary School",
      "grades": "K-5",
      "numberOfStudents": 405,
      "rating": "5/10",
      "distance": 1.9732649557582613
    },
    {
      "type": "public",
      "name": "Harrington Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 289,
      "rating": "4/10",
      "distance": 2.1408492397069607
    },
    {
      "type": "public",
      "name": "Brown Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 627,
      "rating": "5/10",
      "distance": 2.2599420503187644
    },
    {
      "type": "public",
      "name": "Edison Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 576,
      "rating": "5/10",
      "distance": 2.266654798140853
    },
    {
      "type": "public",
      "name": "Swansea Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 486,
      "rating": "2/10",
      "distance": 2.3013202370723405
    },
    {
      "type": "public",
      "name": "Centennial A School for Expeditionary Learning",
      "grades": "PK-5",
      "numberOfStudents": 495,
      "rating": "3/10",
      "distance": 2.3843745448009743
    },
    {
      "type": "charter",
      "name": "Cesar Chavez Academy Denver",
      "grades": "K-8",
      "numberOfStudents": 247,
      "rating": "5/10",
      "distance": 2.4182306621472156
    },
    {
      "type": "charter",
      "name": "Ricardo Flores Magon Academy",
      "grades": "K-8",
      "numberOfStudents": 280,
      "rating": "2/10",
      "distance": 2.4187853329128712
    },
    {
      "type": "public",
      "name": "Columbine Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 260,
      "rating": "3/10",
      "distance": 2.4552840275703085
    },
    {
      "type": "public",
      "name": "Bruce Randolph School",
      "grades": "6-12",
      "numberOfStudents": 739,
      "rating": "3/10",
      "distance": 2.5812571921284504
    },
    {
      "type": "public",
      "name": "Greenlee Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 303,
      "rating": "5/10",
      "distance": 2.633490831148173
    },
    {
      "type": "charter",
      "name": "Pioneer Charter School",
      "grades": "PK-5",
      "numberOfStudents": 238,
      "rating": "5/10",
      "distance": 2.639881399946562
    },
    {
      "type": "charter",
      "name": "Strive Prep - Lake Campus",
      "grades": "6-8",
      "numberOfStudents": 333,
      "rating": "3/10",
      "distance": 2.6464914601700076
    },
    {
      "type": "public",
      "name": "Lake International School",
      "grades": "6-8",
      "numberOfStudents": 342,
      "rating": "2/10",
      "distance": 2.6464914601700076
    },
    {
      "type": "public",
      "name": "Morey Middle School",
      "grades": "6-8",
      "numberOfStudents": 280,
      "rating": "7/10",
      "distance": 2.667372766892018
    },
    {
      "type": "public",
      "name": "Cheltenham Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 397,
      "rating": "4/10",
      "distance": 2.7388448341866853
    },
    {
      "type": "public",
      "name": "Compassion Road Academy",
      "grades": "9-12",
      "numberOfStudents": 197,
      "rating": "1/10",
      "distance": 2.8129278197708376
    },
    {
      "type": "public",
      "name": "Fairview Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 226,
      "rating": "3/10",
      "distance": 2.9001004794698453
    },
    {
      "type": "charter",
      "name": "Girls Athletic Leadership School Middle School",
      "grades": "6-8",
      "numberOfStudents": 327,
      "rating": "5/10",
      "distance": 3.0556656532864404
    },
    {
      "type": "charter",
      "name": "Girls Athletic Leadership School High School",
      "grades": "9-12",
      "numberOfStudents": 136,
      "rating": "3/10",
      "distance": 3.0556656532864404
    },
    {
      "type": "public",
      "name": "East High School",
      "grades": "9-12",
      "numberOfStudents": 2659,
      "rating": "7/10",
      "distance": 3.1119655232952645
    },
    {
      "type": "charter",
      "name": "Venture Prep",
      "grades": "9-12",
      "numberOfStudents": 133,
      "rating": "1/10",
      "distance": 3.117405737451378
    },
    {
      "type": "public",
      "name": "Dora Moore ECE - 8th Grade School",
      "grades": "PK-8",
      "numberOfStudents": 343,
      "rating": "6/10",
      "distance": 3.225528097599016
    },
    {
      "type": "public",
      "name": "Colfax Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 302,
      "rating": "3/10",
      "distance": 3.2379241309791595
    },
    {
      "type": "public",
      "name": "Denver Center For International Studies",
      "grades": "6-12",
      "numberOfStudents": 730,
      "rating": "5/10",
      "distance": 3.278627505499149
    },
    {
      "type": "public",
      "name": "Eagleton Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 399,
      "rating": "4/10",
      "distance": 3.292705171194403
    },
    {
      "type": "public",
      "name": "Valley View K-8",
      "grades": "K-8",
      "numberOfStudents": 428,
      "rating": "4/10",
      "distance": 3.449567645556564
    },
    {
      "type": "public",
      "name": "Edgewater Elementary School",
      "grades": "PK-6",
      "numberOfStudents": 458,
      "rating": "2/10",
      "distance": 3.482512989952403
    },
    {
      "type": "public",
      "name": "Francis M. Day Elementary School",
      "grades": "PK-5",
      "numberOfStudents": 386,
      "rating": "4/10",
      "distance": 3.583744890427132
    }
  ],
  "units": [
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/8d897fe5862853c8728577425edbd826.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-17",
      "id": 33184919,
      "name": "1119",
      "price": 2785,
      "priceMax": 0,
      "remoteListingId": "C-2A.1-1119",
      "sqft": 920,
      "unitRentalId": "p37540959-C-2A.1-1119",
      "updatedAt": "2023-06-15T13:52:39Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=26176441&myOlePropertyId=1231141&floorPlans=3451845&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/86be46cda853ac491291b78c664f22d4.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-09-02",
      "id": 33291902,
      "name": "1715",
      "price": 3005,
      "priceMax": 0,
      "remoteListingId": "C-2A.2-1715",
      "sqft": 938,
      "unitRentalId": "p37540959-C-2A.2-1715",
      "updatedAt": "2023-06-20T13:32:06Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=26176533&myOlePropertyId=1231141&floorPlans=3451854&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/86be46cda853ac491291b78c664f22d4.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-11",
      "id": 28257497,
      "name": "1619",
      "price": 2945,
      "priceMax": 0,
      "remoteListingId": "C-2A.2-1619",
      "sqft": 938,
      "unitRentalId": "p37540959-C-2A.2-1619",
      "updatedAt": "2023-06-07T13:36:40Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=26176520&myOlePropertyId=1231141&floorPlans=3451854&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/1bf3d421bacee950998796914d192339.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-26",
      "id": 33303421,
      "name": "1101",
      "price": 3788,
      "priceMax": 0,
      "remoteListingId": "C-2G-1101",
      "sqft": 1092,
      "unitRentalId": "p37540959-C-2G-1101",
      "updatedAt": "2023-06-20T13:32:06Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=26176433&myOlePropertyId=1231141&floorPlans=3451843&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 0,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/14bd826d8e84c70288d3bb86a0e8e3f6.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-16",
      "id": 33226685,
      "name": "374",
      "price": 1952,
      "priceMax": 0,
      "remoteListingId": "A-0E-374",
      "sqft": 599,
      "unitRentalId": "p37540959-A-0E-374",
      "updatedAt": "2023-06-20T13:32:07Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24128972&myOlePropertyId=1231141&floorPlans=3413537&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/f6a267196aa30b9134d327390fcc4f75.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-05",
      "id": 33024035,
      "name": "33",
      "price": 3538,
      "priceMax": 0,
      "remoteListingId": "ZiaA-2G-33",
      "sqft": 1330,
      "unitRentalId": "p37540959-ZiaA-2G-33",
      "updatedAt": "2023-06-01T13:20:44Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24102860&myOlePropertyId=1231141&floorPlans=3413553&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 0,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/40a4afabf8e652c60ef5d8a857774368.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-05",
      "id": 28676576,
      "name": "569",
      "price": 1839,
      "priceMax": 0,
      "remoteListingId": "A-0A-569",
      "sqft": 486,
      "unitRentalId": "p37540959-A-0A-569",
      "updatedAt": "2023-06-15T13:52:40Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24168966&myOlePropertyId=1231141&floorPlans=3413533&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 1,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/7e882ec7b8921aab5295d6463bf83f65.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-18",
      "id": 33124657,
      "name": "367",
      "price": 1930,
      "priceMax": 0,
      "remoteListingId": "ZiaA-1A-367",
      "sqft": 598,
      "unitRentalId": "p37540959-ZiaA-1A-367",
      "updatedAt": "2023-06-19T13:49:07Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24128967&myOlePropertyId=1231141&floorPlans=3413539&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 1,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/7e882ec7b8921aab5295d6463bf83f65.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-08",
      "id": 32630974,
      "name": "413",
      "price": 1930,
      "priceMax": 0,
      "remoteListingId": "ZiaA-1A-413",
      "sqft": 598,
      "unitRentalId": "p37540959-ZiaA-1A-413",
      "updatedAt": "2023-06-19T13:49:08Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24128978&myOlePropertyId=1231141&floorPlans=3413539&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/65b16c3869729ed86b01007a613523be.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-07-27",
      "id": 32729605,
      "name": "639",
      "price": 3310,
      "priceMax": 0,
      "remoteListingId": "ziaA-2F-639",
      "sqft": 885,
      "unitRentalId": "p37540959-ziaA-2F-639",
      "updatedAt": "2023-05-31T01:36:42Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24168999&myOlePropertyId=1231141&floorPlans=3413551&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 1,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/c26bf9cdf5787ad52bbf9de199243ef1.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-08",
      "id": 30459982,
      "name": "548",
      "price": 1780,
      "priceMax": 0,
      "remoteListingId": "ZiaA-1C-548",
      "sqft": 561,
      "unitRentalId": "p37540959-ZiaA-1C-548",
      "updatedAt": "2023-06-15T13:52:39Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24168950&myOlePropertyId=1231141&floorPlans=3413541&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 1,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/c26bf9cdf5787ad52bbf9de199243ef1.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-09-09",
      "id": 33081744,
      "name": "247",
      "price": 1792,
      "priceMax": 0,
      "remoteListingId": "ZiaA-1C-247",
      "sqft": 561,
      "unitRentalId": "p37540959-ZiaA-1C-247",
      "updatedAt": "2023-06-19T13:49:07Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24102894&myOlePropertyId=1231141&floorPlans=3413541&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 1,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/c26bf9cdf5787ad52bbf9de199243ef1.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-09-02",
      "id": 26981686,
      "name": "249",
      "price": 1792,
      "priceMax": 0,
      "remoteListingId": "ZiaA-1C-249",
      "sqft": 561,
      "unitRentalId": "p37540959-ZiaA-1C-249",
      "updatedAt": "2023-06-19T13:49:07Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24102895&myOlePropertyId=1231141&floorPlans=3413541&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 1,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/19272fc5f88ba3fa2188c0817d832907.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-09-02",
      "id": 33291903,
      "name": "316",
      "price": 2144,
      "priceMax": 0,
      "remoteListingId": "ZiaA-1B-316",
      "sqft": 660,
      "unitRentalId": "p37540959-ZiaA-1B-316",
      "updatedAt": "2023-06-20T13:32:07Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24102916&myOlePropertyId=1231141&floorPlans=3413540&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 0,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/6a1da2951f04c6c872bcda85db2c095d.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-03-07",
      "id": 31186028,
      "name": "236",
      "price": 1712,
      "priceMax": 0,
      "remoteListingId": "A-0G-236",
      "sqft": 564,
      "unitRentalId": "p37540959-A-0G-236",
      "updatedAt": "2023-05-31T01:36:41Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24102890&myOlePropertyId=1231141&floorPlans=3413538&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 0,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/6a1da2951f04c6c872bcda85db2c095d.jpg"
      ],
      "availability": "available",
      "availableOn": "2022-12-17",
      "id": 26934947,
      "name": "270",
      "price": 1712,
      "priceMax": 0,
      "remoteListingId": "A-0G-270",
      "sqft": 564,
      "unitRentalId": "p37540959-A-0G-270",
      "updatedAt": "2023-05-31T01:36:41Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24102905&myOlePropertyId=1231141&floorPlans=3413538&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/4d922adceb017cd4e34253bf846b1128.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-07-01",
      "id": 26905233,
      "name": "439",
      "price": 2875,
      "priceMax": 0,
      "remoteListingId": "ZiaA-2D-439",
      "sqft": 1020,
      "unitRentalId": "p37540959-ZiaA-2D-439",
      "updatedAt": "2023-06-08T13:56:49Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24128997&myOlePropertyId=1231141&floorPlans=3413549&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/95337488b0b74e24b55879ab686c976e.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-22",
      "id": 33213068,
      "name": "31",
      "price": 2892,
      "priceMax": 0,
      "remoteListingId": "ZiaA-2H-31",
      "sqft": 1047,
      "unitRentalId": "p37540959-ZiaA-2H-31",
      "updatedAt": "2023-06-15T13:52:39Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24102859&myOlePropertyId=1231141&floorPlans=3413552&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 0,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/366bc1cdae02552733fda4df2eb84826.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-19",
      "id": 27061047,
      "name": "621",
      "price": 1907,
      "priceMax": 0,
      "remoteListingId": "A-0H-621",
      "sqft": 604,
      "unitRentalId": "p37540959-A-0H-621",
      "updatedAt": "2023-06-15T13:52:40Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=24168987&myOlePropertyId=1231141&floorPlans=3413536&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 1,
      "bed": 0,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/902223536cbe2e59fa0ba22553cacacd.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-05-13",
      "id": 31979815,
      "name": "1121",
      "price": 1755,
      "priceMax": 0,
      "remoteListingId": "C-0A-1121",
      "sqft": 582,
      "unitRentalId": "p37540959-C-0A-1121",
      "updatedAt": "2023-06-19T13:49:07Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=26176442&myOlePropertyId=1231141&floorPlans=3451853&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    },
    {
      "bath": 2,
      "bed": 2,
      "photos": [
        "https://res.cloudinary.com/apartmentlist/image/upload/c_fill,dpr_auto,f_auto,g_center,h_830,q_auto,w_1280/2f6dd2ebebee45809e8b373ddfa39327.jpg"
      ],
      "availability": "available",
      "availableOn": "2023-08-23",
      "id": 27495105,
      "name": "1701",
      "price": 3030,
      "priceMax": 0,
      "remoteListingId": "C-2F-1701",
      "sqft": 997,
      "unitRentalId": "p37540959-C-2F-1701",
      "updatedAt": "2023-06-20T13:32:07Z",
      "applyOnlineUrl": "http://liveziadenver.securecafe.com/onlineleasing/zia/oleapplication.aspx?stepname=RentalOptions&UnitID=26176523&myOlePropertyId=1231141&floorPlans=3451861&src=21&rcstdid=MTQ%3d-pGJGpRzZiM8%3d"
    }
  ]
}
```

## Contact 
Please visit us through [epctex.com](https://epctex.com) to see all the products that is available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
