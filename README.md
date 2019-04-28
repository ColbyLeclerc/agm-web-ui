## TOC
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installing & Local Development](#installing--local-development)
- [Files/Folder Structure](#filesfolders-structure)
- [Deployment](#deployment)
- [License](#license)


## Getting Started
In order to run **Adminator** (Original name of the template) on your local machine, install the prerequisites on your machine and follow the installation steps down below.

#### Prerequisites
  - Node.js
  - Yarn or NPM
  - Git
  - libpng-dev *linux only*

#### Installing & Local Development
Start by typing the following commands in your terminal in order to get **Adminator** full package on your machine and starting a local development server with live reload feature.

```
> cd agm-web-ui
> npm install
> npm run dev
```

Once the dev server is running, see the terminal for the port used to connect. The endpoints used connect to the server `localhost:8080`, thus have `agm-api` running on localhost:8080.

NOTE: Auth keys defined in project are dev keys, belonging only to local instances.

To change the Auth key, go to the following files, and replace the `AUTH_KEY` variable with the new auth key (found at the top of each file):
  - `index.html`
  - `forms.html`
  - `enclosure-detail.html`


##### Troubleshooting
If you get an error similar to below (regarding `transform-vue-jsx` not existing)

```
ERROR in ../assets/scripts/index.js
Module build failed: ReferenceError: Unknown plugin "transform-vue-jsx" specified in "<root-dir>/agm-web-ui/.babelrc" at 0, attempted to resolve relative to "<root-dir>/agm-web-ui"
    at <root-dir>/agm-web-ui/node_modules/babel-core/lib/transformation/file/options/option-manager.js:180:17
    at Array.map (<anonymous>)
    at Function.normalisePlugins (<root-dir>/agm-web-ui/node_modules/babel-core/lib/transformation/file/options/option-manager.js:158:20)
    at OptionManager.mergeOptions (<root-dir>/agm-web-ui/node_modules/babel-core/lib/transformation/file/options/option-manager.js:234:36)
    at OptionManager.init (<root-dir>/agm-web-ui/node_modules/babel-core/lib/transformation/file/options/option-manager.js:368:12)
    at File.initOptions (<root-dir>/agm-web-ui/node_modules/babel-core/lib/transformation/file/index.js:212:65)
    at new File (<root-dir>/agm-web-ui/node_modules/babel-core/lib/transformation/file/index.js:135:24)
    at Pipeline.transform (<root-dir>/agm-web-ui/node_modules/babel-core/lib/transformation/pipeline.js:46:16)
    at transpile (<root-dir>/agm-web-ui/node_modules/babel-loader/lib/index.js:50:20)
    at Object.module.exports (<root-dir>/agm-web-ui/node_modules/babel-loader/lib/index.js:173:20)
 @ multi ../assets/scripts/index.js
```

then you'll have to install the dependency manually:
```
> npm install\
  babel-plugin-syntax-jsx\
  babel-plugin-transform-vue-jsx\
  babel-helper-vue-jsx-merge-props\
  babel-preset-env\
  --save-dev
```

## Files/Folders Structure
Here is a brief explanation of the template folder structure and some of its main files usage:

```
└── src                         # Contains all template source files.
│   └── assets                  # Contains JS, CSS, images and icon fonts.
│   │   └── scripts             # Contains all JavaScript files.
│   │   │   └── charts          # Chart.js, Sparkline & Pie Chart plugins init.
│   │   │   └── chat            # All chat app JS code.
│   │   │   └── constants       # Template constant values like color values.
│   │   │   └── datatable       # Date table plugin init.
│   │   │   └── datepicker      # Bootstrap datepicker init.
│   │   │   └── email           # All email app code.
│   │   │   └── fullcalendar    # Fullcalendar plugin init.
│   │   │   └── googleMaps      # Google maps API integration code.
│   │   │   └── masonry         # Masonry layout code.
│   │   │   └── popover         # Bootstrap popover plugin init.
│   │   │   └── scrollbar       # Perfect scrollbar plugin init.
│   │   │   └── search          # Topbar toggle search init.
│   │   │   └── sidebar         # Sidebar JS code.
│   │   │   └── skycons         # Animated icons plugin init.
│   │   │   └── utils           # Basic utils used for proper rendering.
│   │   │   └── vectorMaps      # Vector maps plugin init.
│   │   │   └── index.js        # Indicator file.
│   │   │
│   │   └── static              # Contains the non-code files.
│   │   │   └── fonts           # Contains icon fonts.
│   │   │   └── images          # Contains all template images/svg.
│   │   │
│   │   └── styles              # Contains all SCSS files.
│   │       └── spec            # Contains custom SCSS files.
│   │       │   └── components  # Contains all template components.
│   │       │   └── generic     # Contains basic scaffolding styles.
│   │       │   └── screens     # Contains views specific styles.
│   │       │   └── settings    # Contains all template variables.
│   │       │   └── tools       # Contains all mixins.
│   │       │   └── utils       # Contains helper classes.
│   │       │   └── index.scss  # Indicator file.
│   │       │
│   │       └── vendor          # Contains all plugin files & custom styles.
│   │       └── index.scss      # Indicator file.
│   │
│   └── *.html                  # All HTML pages files .
└── webpack                     # Contains Webpack init code.
│   └── plugins                 # Contains all Webpack plugins config.
│   └── rules                   # Contains Loaders config code.
│   └── config.js               # Contains Webpack config object.
│   └── devServer.js            # Webpack dev server config code.
│   └── manifest.js             # All build system constants.
│
└── .babelrc                    # Babel ES6 Transpiler.
└── .editorconfig               # Keep same coding styles between code editors.
└── .eslintrc.yml               # JavaScript Linting.
└── .gitattributes              # Git Attributes.
└── .gitignore                  # Ignored files in Git.
└── .stylelintrc.yml            # SCSS/CSS Linting.
└── browserslist                # Supported Browsers.
└── CHANGELOG.md                # Versioning.
└── package.json                # Package metadata.
└── README.md                   # Manual file.
└── webpack.config.js           # Webpack main config file.
└── yarn.lock                   # Yarn metadata.
```

## Deployment
In deployment process, you have two commands:

1. Build command
Used to generate the final result of compiling src files into build folder. This can be achieved by running the following command:
```
> npm run build
```

2. Preview command
Used to create a local dev server in order to preview the final output of build process. This can be achieved by running the following command:
```
> npm run preview
```

## Built With
- [Babel](https://babeljs.io/)
- [Webpack](https://webpack.js.org/)
- [Eslint](https://eslint.org/)
- [Sass](http://sass-lang.com/)
- [Postcss](http://postcss.org/)
- [Stylelint](https://stylelint.io/)
- [Bootstrap](http://getbootstrap.com/)
- [Chart.js](http://www.chartjs.org/)
- [Datatables](https://datatables.net/)
- [Jquery](https://jquery.com/)
- [Lodash](https://lodash.com/)
- [Masonry](https://masonry.desandro.com/)
- [Moment](https://momentjs.com/)
- [Perfect Scrollbar](https://github.com/utatti/perfect-scrollbar)
- [Skycons](https://darkskyapp.github.io/skycons/)
- [Fontawesome](http://fontawesome.io/)
- [Themify Icons](https://themify.me/themify-icons)
- [Roboto Font](https://fonts.google.com/specimen/Roboto)

## License

Adminator is licensed under The MIT License (MIT). Which means that you can use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the final products. But you always need to state that Colorlib is the original author of this template.
