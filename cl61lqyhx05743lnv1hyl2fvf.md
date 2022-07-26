## Introducing opendeck: The open source deck building community

This month I decided to participate in the [Hashnode x PlanetScale Hackathon](https://townhall.hashnode.com/planetscale-hackathon?source=hashnode_countdown) and built opendeck, an open source deck building community that facilitates the creation and organization of playable cards. Opendeck has 2 main paths of use, the first allows you to create custom cards and organize them in decks and the second allows you to consume these cards and decks via a public API in your own custom games. I love playing games and I hope to develop my own in the future, but the one thing that has kept me from creating one is the number of assets needed to create a game. Let's say I wanted to create a card game. As a developer, I could write scripts to handle the game mechanics but what happens when I need to populate the game with content? With opendeck, I aim to close that gap by providing a library of open-sourced assets created by the community.

[Live app](https://opendeck.dev)

[GitHub Repo](https://github.com/huntertrammell/opendeck.io)

## Tech Stack

- Next.js
- TypeScript
- Tailwind CSS
- PlanetScale
- Prisma
- Supabase (image storage)

## **Features**

### **Global alert system**
Created a pubsub to handle dynamic component rendering for API-driven components such as card/deck creation forms and pagination/sorting. More information on how this works can be [found on my blog](https://huntertrammell.dev/blog/how-to-create-a-dynamic-alert-component-in-react).

### **Live card editing**
When creating and editing your cards you can see your card updates in real-time.

### **Public API**
Built to be consumed via custom games, the public API allows you to query cards and decks created by the community. There is also an insomnia package that includes all the routes for more detailed examples.

### **Rate Limiting**
The public API has rate limiting in place to help keep the server load contained. API calls are limited to 50 calls per minute.

### **Community driven XP system**
Cards have levels determined by the XP assigned to a card. Each authenticated user can assign 15pts of XP to each card, once the card has 200XP it will gain a level.

## **Working with PlanetScale**
Before this application, I had never used the PlanetScale platform but found it quite intuitive with a user-friendly interface. I generally lean more towards front-end development so I was a bit unsure about how working with an ORM and a database would work out but it honestly was pretty painless. PlanetScale had everything I needed from tutorials to connection settings for Prisma. I was able to get up and running quickly and without a ton of configuration which was nice.

## **Challenges**
The biggest challenges I faced in this project were getting the image upload capability working as well as creating the schema for the oAuth user tables in the database. When using Prisma as a database provider with NextAuth there are a few more tables needed to hold user data and It took a bit of digging to get that working.

## Conclusion

Overall I learned a lot and had fun using PlanetScale and the other technologies in my stack. Excited to see the opendeck database grow and the games that will come out of it. What will you create?

