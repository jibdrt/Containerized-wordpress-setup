'use strict';

var gulp = require('gulp');
var sass = require('gulp-sass')(require('sass'));
var concat = require('gulp-concat');
var uglify = require('gulp-uglify');


function buildSass() {
    return gulp.src('./assets/scss/style.scss')
        .pipe(sass().on('error', sass.logError))
        .pipe(gulp.dest('./'));
}

function buildJs() {
    return gulp.src('./assets/js/components/**/*.js')
        .pipe(concat('global.js'))
        .pipe(uglify())
        .pipe(gulp.dest('./assets/js/'))
}

function buildBlocksSass() {
    return gulp.src('./assets/scss/blocks/*.scss')
        .pipe(sass().on('error', sass.logError))
        .pipe(gulp.dest('./assets/css/blocks/'));
}

exports.buildSass = buildSass;
exports.buildJs = buildJs;
exports.buildBlocksSass = buildBlocksSass;

exports.watch = function () {
    gulp.watch('./assets/scss/**/*.scss', buildSass);
    gulp.watch('./assets/js/components/**/*.js', buildJs);
    gulp.watch('./assets/scss/blocks/*.scss', buildBlocksSass);
};