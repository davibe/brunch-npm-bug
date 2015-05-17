Do this:

    npm install .
    brunch build

The result public/app.js should have export definition for both 'jquery' and
'trifl' instead it only has that for 'jquery'.

Looks like brunch can't properly handle trifl.


i.e. there is

    ...
    require.register('jquery', function (exp, req, mod) {
        ...

but instead of
    
    ...
    require.register('trifl', function (exp, req, mod) {
        ...

there is something like

    ...
    require.register('individual', function (exp, req, mod) {
        ...

