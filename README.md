<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

🔗 **Live Website:** [Click here to view](http://nextwork-website-project-yosephalramahi.s3-website.us-east-2.amazonaws.com/)

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** Yoseph Alramahi  
**Email:** yoseph.h.ramahi@gmail.com

---

![Image](http://learn.nextwork.org/gleeful_blue_proud_eagle/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

In this project, I will demonstrate how to host a Website on Amazon S3

### Tools and concepts

The service I used was Amazon S3. Key concepts I went through include bucket policies, uploading static website files, using index.html, the bucket endpoint URL, and how ACLs control access to files.

### Project reflection

This project took me approximately an hour. The most challenging part was the 403 error. It was most rewarding to see my webpage load live and be public to the world. 

---

## How I Set Up an S3 Bucket

Creating an S3 bucket took me few minutes.

The Region I picked for my S3 bucket was ohio because it's the region that's closest to me. 

S3 bucket names must be globally unique. This means no two S3 buckets anywhere in the world can have the same name.

![Image](http://learn.nextwork.org/gleeful_blue_proud_eagle/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### index.html and image assets

I uploaded two files to my S3 bucket. One was the index.html file, which controls what shows up on my website. The other was a folder with images and assets; this adds pictures and things to look at on the website.

Both files are needed. The index.html sets up the website’s structure, but that alone isn’t enough. If it says to show an image, the image must also be uploaded. Without the actual files (like images), the site can’t display everything correctly. 

![Image](http://learn.nextwork.org/gleeful_blue_proud_eagle/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

Website hosting means storing your website files on a server so people can access your site through the internet.

To enable website hosting with my S3 bucket, I turned on the static website hosting option and selected index.html as the main file.

An ACL (Access Control List) is a way to configure permissions. We enable ACLs to control access to our files later.

![Image](http://learn.nextwork.org/gleeful_blue_proud_eagle/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

Once static website hosting is enabled, S3 gives you a bucket endpoint URL, which is the link you can use to visit your website in a browser.

When I first visited the bucket endpoint URL, I saw an "Access Denied" error. The reason for this was that the bucket permissions did not allow public access to the files yet.

![Image](http://learn.nextwork.org/gleeful_blue_proud_eagle/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

To resolve this 403 Forbidden error, I made the files public by enabling read access through the ACL

![Image](http://learn.nextwork.org/gleeful_blue_proud_eagle/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

An alternative to ACLs is bucket policies. Bucket policies work like rules that define who is allowed or not allowed to do certain actions with the files in a bucket. The main benefit of using bucket policies is that they give you more detailed control over access. You can specify what actions are allowed (like read, write, or delete) and for which users, IP addresses, or AWS accounts.

While ACLs are useful for quickly making files public or setting basic permissions on individual files, bucket policies are better for managing permissions at the bucket level, especially when dealing with more complex access requirements.

My bucket policy is set to deny everyone from deleting the HTML file. I tested it by trying to delete index.html and received a "Permission Denied" error. This confirmed that the bucket policy worked and successfully protected the object from being deleted.

![Image](http://learn.nextwork.org/gleeful_blue_proud_eagle/uploads/aws-host-a-website-on-s3_sm2sm2sm)

---
