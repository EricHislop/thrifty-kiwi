---
title: "Aws Amplify React"
description: 
date: 2023-03-23T22:14:39+13:00
image: cover.png
math: 
license: 
hidden: false
comments: true
draft: false
categories:
    - Tutorials
tags:
    - AWS
    - Amplify
    - GraphQL
    - React
---

# How to Build a Subscription Sharing App with React, AWS Amplify, and GraphQL

In this tutorial, we'll build a web application for tracking and sharing subscription services like Netflix, Spotify, and YouTube. We'll use React for the frontend, AWS Amplify for the backend, and GraphQL for our API.

## Prerequisites

- Basic knowledge of JavaScript and React
- An AWS account
- Node.js and npm installed on your machine

## Step 1: Set Up Your React App

Create a new React app using 
`npx create-react-app kiwishare`
Change to the project directory:

`cd kiwishare`


Install the necessary dependencies:

`npm install aws-amplify @aws-amplify/ui-react`

## Step 2: Install and Configure the Amplify CLI

Install the Amplify CLI globally:

`
npm install -g @aws-amplify/cli
`

Configure the Amplify CLI with your AWS account:

`
amplify configure
`

Follow the prompts to complete the configuration process.

## Step 3: Initialize Amplify

`
amplify init
`

Follow the prompts to complete the Amplify initialization process.

## Step 4: Add Auth and API

Add authentication to your app:

`
amplify add auth
`

Add a GraphQL API:

`
amplify add api
`

Choose the "Amazon DynamoDB" as the data source.

## Step 5: Define Your GraphQL Schema

Edit the `schema.graphql` file to define the data model for your app:

```graphql
type StreamingService
  @model
  @auth(rules: [{ allow: owner }])
{
  id: ID!
  name: String!
  description: String
  price: Float!
  sharings: [Sharing] @hasMany(indexName: "byStreamingService", fields: ["id"])
}

type Sharing
  @model
  @auth(rules: [{ allow: owner }])
{
  id: ID!
  title: String!
  streamingServiceID: ID! @index(name: "byStreamingService")
  streamingService: StreamingService! @belongsTo(fields: ["streamingServiceID"])
}
```

## Step 6: Deploy Your Backend

`amplify push`

This command will create and configure the necessary backend resources in your AWS account.

## Step 7: Update Your React App

Integrate Amplify into your React app by adding the necessary imports and configurations.

## Step 8: Run Your App

`npm start`

Your app should now be running on [http://localhost:3000](http://localhost:3000). You can now sign up, sign in, and start using the app to track and share subscription services!

## Conclusion

In this tutorial, we built a subscription sharing app using React, AWS Amplify, and GraphQL. We learned how to set up a React app, configure Amplify, define a GraphQL schema, and deploy our backend to AWS. This is just the beginning – you can now customize and expand your app to add more features and functionality!

Happy coding! 🚀