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
git add .

git config --global user.email "jbsenapps@gmail.com"
git config --global user.name "jbs1972"

git commit -m "first commit"
git branch -M main

git branch
git remote add origin https://github.com/jbs1972/git_react_demo.git
git push -u origin main

create a new folder "branches"
cd .\branches\
git clone https://github.com/jbs1972/git_react_demo.git
cd .\git_react_demo\

npm i
npm start

git checkout -b feature/footer
git branch

Create a new file Footer.js in the new branch:
=>
function Footer() {
  return (
    <footer className="text-center mt-10">
      <p>© 2025 React Lab Project</p>
    </footer>
  );
}
export default Footer;

git status
git add .
git commit -m "Footer.js component added"
git push origin feature/footer

git checkout main
git branch

git merge feature/footer
git log -> q to exit
git log --oneline --graph

git branch -d feature/footer
git branch -D feature/footer (force delete)
 - This command deletes the local copy of the branch from your machine.
git push origin --delete feature/footer
 - This command deletes the branch from the remote server (e.g., GitHub, GitLab, or Bitbucket).

