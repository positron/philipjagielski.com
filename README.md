# My site
The [Jekyll][j] source for [philipjagielski.com][pj].

## Running a development server
- Install Jekyll: `gem install jekyll`
- Clone this repository: `git clone https://github.com/positron/philipjagielski.com.git`
- Run the Jekyll server: `jekyll serve --watch`
- Now view the result at [localhost:4000][local]

## Publishing to S3
- Install s3_website: `gem install s3_website`
- Set the environment variables `pj_s3_id` and `pj_s3_secret` to the IAM credentials for a user with * access to the S3 bucket.
- Run `s3_website push`

## First time creation
- Change the S3 bucket in the config file 
- Run `s3_website cfg apply` to create and configure the bucket for static web hosting.
- Set a Route53 ALIAS record to the S3 bucket

## Credits
I'm using the [Lagom][lagom] theme that [@\_swanson][swanson] designed for his
personal website. One day, I'd like to design my own theme from scratch, but
I'm slow at web design and I'm currently focused on other projects.

## Contact
Feel free to open issues if you run into trouble or have suggestions. Pull
Requests are always welcome, especially for grammar and spelling corrections :)

## License
The following directories and their contents are copyright Philip Jagielski.
You may not reuse anything therein without my permission:

* `_posts/`

All other directories and files are MIT Licensed.

[j]: http://jekyllrb.com/
[pj]: http://philipjagielski.com/
[local]: http://localhost:4000/
[lagom]: https://github.com/swanson/lagom
[swanson]: https://twitter.com/_swanson
