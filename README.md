# Full Static with NuxtJS and Storyblok

A boilerplate project designed to demonstrate the benefits of using Jamstack and the easy configuration of a project with NuxtJS and Storyblok.

## Storyblok space Setup

In this section we are going to look at how to define the component schemas needed for this project in our Storyblok space. What properties, type of fields, we have in each one and, finally, we will see an example of using these components to create a new page.

### Create an account and start an space in Storyblok

Go to [app.storyblok.com](https://app.storyblok.com/#!/), select *Sign up* and create an account. When it's ready, create an empty space and follow the next steps.

### Blocks schema

![Components and templates at Storyblok Full Static site](https://i.imgur.com/aXNbCyPh.png)

**Content type**

#### 1. Page template
 
| Field Name | Field Type | Options                                                            |
| ---------- | ---------- | ------------------------------------------------------------------ |
| title      | Text       |                                                                    |
| body       | Blocks     | Allow only specific components to be inserted: Groups -> Organisms |

![Page template Storyblok schema](https://i.imgur.com/cm46ze3h.png)

#### Body

![Body block options](https://i.imgur.com/85S4pdeh.png)

**Nestable Molecules**

#### 1. Heading Section

| Field Name   | Field Type |
| ------------ | ---------- |
| subtitle     | Text       |
| title        | Text       |
| intro        | Textarea   |
    
![Heading Section Storyblok schema](https://i.imgur.com/0qFyFC5h.png)

#### 2. Benefit Card

| Field Name   | Field Type        | Options                                                                                          |
| ------------ | ----------------- | ------------------------------------------------------------------------------------------------ |
| icon         | Asset             | Images                                                                                           |
| color        | Single-Option     | Source: self; Options (name/value): orange/orange, purple/purple, blue/blue, green/green         |
| name         | Text              |                                                                                                  |
| description  | Textarea          |                                                                                                  |

    
![Benefit Card Storyblok schema](https://i.imgur.com/BasBxc1h.png)
    
Color single-option definition:

![Benefit Card Color single-option definition](https://i.imgur.com/KsGclwEh.png)

#### 3. Tech Card

| Field Name   | Field Type | Options             |
| ------------ | ---------- | ------------------- |
| logo         | Asset      | Images              |
| name         | Text       |                     |
| url          | Link       |                     |

![Tech Card Storyblok schema](https://i.imgur.com/Eg6Jl2sh.png)

**Nestable Organisms**

#### 1. Benefits

| Field Name   | Field Type | Options                                                                             |
| ------------ | ---------- | ----------------------------------------------------------------------------------- |
| heading      | Blocks     | Allow only specific components to be inserted: Component -> Heading Section (1 max) |
| benefits     | Blocks     | Allow only specific components to be inserted: Component -> Benefit Card (6 max)    |

![Benefits Storyblok schema](https://i.imgur.com/IYrf7qZh.png)

| Heading                                                         | Benefits                                                       |
| --------------------------------------------------------------- | -------------------------------------------------------------- |
| ![Heading Blocks definition](https://i.imgur.com/uOr3xLJh.png)   | ![Benefits Blocks definition](https://i.imgur.com/kt0Ur2Ph.jpg) |

#### 2. Tech Stack

| Field Name   | Field Type | Options                                                                             |
| ------------ | ---------- | ----------------------------------------------------------------------------------- |
| heading      | Blocks     | Allow only specific components to be inserted: Component -> Heading Section (1 max) |
| stack        | Blocks     | Allow only specific components to be inserted: Component -> Tech Card               |

![Tech stack Storyblok schema](https://i.imgur.com/U2xjfvAh.png)

| Heading                                                         | Benefits                                                        |
| --------------------------------------------------------------- | --------------------------------------------------------------- |
| ![Heading Blocks definition](https://i.imgur.com/TE7NdhLh.png)   | ![Tech card Blocks definition](https://i.imgur.com/C8yL3Cih.png) |

## Components use case: Homepage

For the homepage we will fill in the title field and choose the organisms we want in the body.

> In this example, as in the live demo, we'll add Benefits and Tech Stack organisms.

![Homepage template filled with title and body organisms](https://i.imgur.com/LyxhvNgh.png)

And this is how the home Config tab will look like:

![Page template configuration in Storyblok](https://i.imgur.com/5doP0aHm.png)

For the organisms, let's see which blocks to add to them:

### Benefits Organism Content

#### 1. Adding a Heading Section molecule
![Adding a heading section to the Benefits organism](https://i.imgur.com/9DjwZmlh.png)

#### 2. Adding Benefit Card molecules
![Adding a benefit card to the Benefits organism](https://i.imgur.com/5JlmwTxh.png)


### Tech Stack Organism Content

#### 1. Adding a Heading Section molecule
![Adding a heading section to the Tech Stack organism](https://i.imgur.com/5sPli8hh.png)

#### 2. Adding Tech Card molecules
![Adding a tech card to the Tech Stack organism](https://i.imgur.com/709Wnauh.png)



## Frontend Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
