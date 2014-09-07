# Vinylify

Simple plugin for a smoother browserify/gulp workflow. 

Monkey patches b.bundle to return a vinyl buffer object for further processing with gulp.

```javascript
gulp.task('build', function() {
  return browserify('file.js')
    .plugin('vinylify')
    .bundle('out.js')
    .pipe(uglify())
    .pipe(gulp.dest('build/'));
});
```

Or require and call vinylify directly to return browserify with the plugin applied.

```javascript
gulp.task('build', function() {
  return vinylify('file.js')
    .bundle('out.js')
    .pipe(uglify())
    .pipe(gulp.dest('build/'));
});
```
