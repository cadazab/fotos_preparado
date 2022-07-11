# foto preparau

## to work:
 * go to directory
 * `npm install`
 * `npm run dev`
 * go to link that is displayed
 
## to upload:
 * npm run build
 * replace the `favicon.ico` file
 * open `index.html` and change:
   ```
    <script type="module" crossorigin src="/assets/index.e9f166f0.js"></script>
    <link rel="stylesheet" href="/assets/index.87c7bdb9.css">
    ```
    to 
   ```
    <script type="module" crossorigin src="./assets/index.e9f166f0.js"></script>
    <link rel="stylesheet" href="./assets/index.87c7bdb9.css">
    ```
    (`./` instead of `/` as a link base)
 * add background color to the body (e.g. `background-color: red;`)
 * content of newly created subdirectory `dist` to web server
