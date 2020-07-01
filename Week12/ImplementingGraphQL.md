## Introducing GraphQL
Basically, GraphQL is a syntax that describes how to ask for information, it is used to load data from a server to a client and prioritizes giving clients exactly the information requested and nothing else. As an alternative to REST, GraphQL allows us to make requests from one to many data sources from a single API call. GraphQL rests between the client and one or more data sources. The problem using REST which maintains multiple endpoints, often slow loading of applications down, more so, when working on your mobile application with all the factors in the mix. 

## Implementing
To run a GraphQL powered application you need to have a GraphQL server that serves your API, for my project I implemented Apollo Server a library that helps with connecting to GraphQL schema to GraphQL server in Node.js. Apollo server is compatible with any GraphQL client. Secondly, a GraphQL client that connects to your endpoints.  

*A recent version of Node.js (8+) is required and being a little familiar to JavaScript is handy.*

__Backend__ 
* I installed [Apollo server](https://www.apollographql.com/docs/apollo-server/getting-started/) this was not a bad experience the guide is well documented.
* Installed GraphQL extension into my vs code editior
* Used Altair to test queries

__Frontend__ 
* Adapted and merged GraphQL using the provided and recommended [installation guide](https://apollo.vuejs.org/guide/installation.html), there were a couple of places I was alittle flabbergasted but with a just trying a few ...alot of alternative methods GraphQL finally emerged.
* Installed Apollo GraphQL extension into my vs code editor 

To install Apollo Server is simply __npm install apollo-server graphql__ it is the core library for Apollo server and works well with the Express server I have in my project.

__Components__
Schemas, resolvers, and queries are the three key ingredients a GraphQL API is organized.
Schema maintains and defines all the possible data that a client can query. In my schema I am querying all my auctions by:
*	_id
*	title
*	description
*	currentBid
*	date

This simple GraphQL schema will allow a client to run this query named Auction and the server will render out one or many Auctions. Next was defining my dataset, Apollo server can get data from any source it is connected to. 

The GraphQL server will not know what to fetch unless you get the resolver involved. The resolver tells GraphQL where to get the auction(s) from. Abit like having a personal secretary, you tell them what you require or need done for the day.

Altair to test my queries is recommended, easy to use and perfect for testing.
Once this was connected and working, all that was required was to adapt the frontend to have the auctions render to the website.

## Problems Encountered
I followed a well-documented tutorial https://www.apollographql.com/docs/apollo-server/getting-started/ that being said, figuring out where to place code had me combing through my files working out where snippets of code should be. 
Defining the Resolver was not a highlight for an inexperienced developer like myself, it all came down to trying out what works. 

## Summary
GraphQL provides a performance boost and once you get your head around resolvers, schemas, and queries GraphQL is relatively easy to implement into your existing application, currently GraphQL is working side by side with Vuex, a state management technology working within my Vue.js. That in my opinion is considered a positive, GraphQL is complementing my application without me having to tear the whole RESTful ecosystem of API design down. However, GraphQL is relatively new and will have pitfalls. 