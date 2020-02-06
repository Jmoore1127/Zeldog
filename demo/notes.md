aws s3api create-bucket --bucket frontend-craftsmen-zeldog-demo2 --acl public-read --region us-west-2 --create-bucket-configuration LocationConstraint=us-west-2
aws s3api put-bucket-policy --bucket frontend-craftsmen-zeldog-demo2 --policy file://bucket-policy.json
aws s3 website s3://frontend-craftsmen-zeldog-demo2/ --index-document index.html
aws s3 cp . s3://frontend-craftsmen-zeldog-demo2/ --recursive --exclude ".git/*" --exclude "demo/*"
open http://frontend-craftsmen-zeldog-demo2.s3-website.us-west-2.amazonaws.com/
