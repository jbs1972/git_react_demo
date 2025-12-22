npm i -D tailwindcss@3 postcss autoprefixer

Plugin Ecosystem Integration:
- By using PostCSS, you can "chain" multiple tools together in a single build step. For example:
        1. Tailwind generates the utility classes.
        2. Autoprefixer (another PostCSS plugin) then takes that generated CSS and adds vendor prefixes (like -webkit-).
        3. Other Plugins can be added for extra features like nesting (Sass-like syntax) or minification (via cssnano).

npx tailwindcss init

"./src/**/*.{js,ts,jsx,tsx,html}"

@tailwind base;
@tailwind components;
@tailwind utilities;

.postcssrc
=>
{
  "plugins": {
    "tailwindcss": {},
    "autoprefixer": {}
  }
}

@parcel/transformer-postcss: Parcel includes CSS transpilation and vendor prefixing by default. PostCSS 
config .postcssrc contains the following redundant plugins: autoprefixer. Removing these may improve    
build performance.
                                                                                                        
  C:\Users\senjb\my_react\git_demo\git_react_demo\.postcssrc:4:5                                        
    3 |     "tailwindcss": {},
  > 4 |     "autoprefixer": {}
  >   |     ^^^^^^^^^^^^^^

This warning occurs because Parcel 2+ includes a built-in CSS transformer (called Lightning CSS) that handles vendor prefixing and transpilation automatically. That is, parcel already performs the same task as the autoprefixer plugin.
Performance: PostCSS is written in JavaScript and is slower than Parcel’s built-in engine, which is written in Rust. Running autoprefixer through PostCSS forces Parcel to run an extra, unnecessary process, which increases build times.

{
  "plugins": {
    "tailwindcss": {}
  }
}

"browserslist": "> 0.5%, last 2 versions, not dead"

The query > 0.5%, last 2 versions, not dead breaks down into three specific filters: 
    1. > 0.5%: Supports any browser that currently has more than 0.5% of the global market share.
    2. last 2 versions: Supports the last two major versions of every browser (e.g., the two most recent versions of Chrome, Safari, and Firefox).
    3. not dead: Excludes "dead" browsers, which are defined as those that have not had official support or maintenance updates in the last 24 months (this primarily excludes Internet Explorer 11).

npm uninstall autoprefixer

git init
git status
