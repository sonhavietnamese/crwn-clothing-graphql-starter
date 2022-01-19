# CRWN-CLOTHING-GRAPHQL-STARTER

This template will use for [Udemy GraphQL Section](https://www.udemy.com/course/complete-react-developer-zero-to-mastery).

## Motivation

There's a lot of problems when follow this course when code along the video section. Because of library version isn't match from current and in the video (I guess most of the videos in this course was recorded in aroung 2019 - 2020). Some of libraries version aren't support or conflict to each others so far.
Ex: In this course, Yihua (the lecture) was using `react-script@3.0.0` and `node-sass@4.12.0`. You may get an error which is `Node Sass does not yet support your current environment`. You may need to use `sass` instead. unfortunately, `react-scripts@3.0.0` which bundled by Webpack 4.19 which did not include `.sass` file loader. So you may need to upgrade react-scripts to `react-script@5.0.0` to compile `sass` file.

In this Udemy lesson, will use 3 libraries which are `apollo-boost`, `react-apollo` and `graphql`. If you running on your own project or [start of lesson project](https://github.com/ZhangMYihua/graphql-lesson) you will get the error:

![Full error image](./repo-img/error.png 'Error cause by Webpack 5 and graphql')

Because of currently, we use `react-scripts@5.0.0` which bundled by Webpack 5. unfortunately, Webpack 5 causes an error with `graphql` library (shown above). How I fix these errors and step by step to fix by your own is in (this section)[https://github.com/sonhaaa/crwn-clothing-graphql-starter#fix-in-existing-code]

## Usage

1. Clone the repo
2. Run `npm install` or `yarn`
3. Run `npm start` or `yarn start`

## Fix in Existing Code

If you want to fix error directly in your code. Follow these step:

1. Run `npm run eject`
2. Go to `config/webpack.config.js`
3. Move to `line 340`
4. Include these config following

```
  {
    test: /\.m?js/,
    resolve: {
      fullySpecified: false,
    },
  },
```

5. Your config file will look like this

```
  rules: [
    {
      test: /\.m?js/,
      resolve: {
        fullySpecified: false,
      },
    },
  ...
 ]
```

**Note: After run `npm eject`, when you open any file \*.(jsx|js) it may have an red underline in very top of these file. Just ignore it and continue to code.**
