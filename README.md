# Apollo Server with offline playground support

This repository shows how to modify the [Apollo Server getting started](https://www.apollographql.com/docs/apollo-server/getting-started.html) application to support running GraphQL Playground while offline.

For full functionality, prisma/graphql-playground#845 needs to be merged and included in the @apollographql/graphql-playground fork.

In the meantime, some manual setup is needed:

- `git clone git@github.com:prisma/graphql-playground.git`
- (if PR not merged, point to penx:feature/cdn-url-config-option fork:branch)
- `cd graphql-playground/packages/graphql-playground-html`
- `yarn`
- edit package.json and add the @apollographql scope to the package name
- `yarn link`
- cd to the clone of this project
- `yarn`
- `yarn link @apollographql/graphql-playground-html`
- `yarn start`

You should now be able to navigate to http://localhost:4000/graphql and see GraphQL playground load - inspect source and you should see the scripts and styles in the head are now loading from localhost rather than the CDN.
