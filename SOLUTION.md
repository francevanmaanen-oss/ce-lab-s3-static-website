# Lab Solution: Host a Static Website on Amazon S3

**Student Name:** France van Maanen
**Date:** 22 April 2026
**Lab Completion Time:** 60 minutes

---

## Part 1: Bucket Configuration

### Bucket Information

**Bucket Name:** acton-static-website-francevm-2026

**Region:** eu-central-1

**Bucket Website Endpoint URL:**
```
http://acton-static-website-francevm-2026.s3-website.eu-central-1.amazonaws.com
```

**Screenshot 1: Bucket Creation Confirmation**
![Bucket Created](screenshots/01-bucket-created.png)

---

## Part 2: Static Website Hosting Configuration

### Configuration Details

**Index Document:** index.html

**Error Document:** error.html

**Screenshot 2: Static Website Hosting Settings**
![Static Hosting Config](screenshots/02-static-hosting-config.png)

---

## Part 3: Website Files

### Files Created

List the files you created:
1. index.html
2. style.css
3. error.html

**Did you customize the HTML/CSS?** (Yes/No): No

**If yes, describe your customizations:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

**Screenshot 3: Files Uploaded to S3**
![Files in S3](screenshots/03-files-uploaded.png)

---

## Part 4: Bucket Policy

### Bucket Policy Applied

**Paste your complete bucket policy here:**
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::acton-static-website-francevm-2026/*"
        }
    ]
}

**Screenshot 4: Bucket Policy Configuration**
![Bucket Policy](screenshots/04-bucket-policy.png)

---

## Part 5: Testing and Verification

### Website Testing

**Website URL (from endpoint):**
```
http://acton-static-website-francevm-2026.s3-website.eu-central-1.amazonaws.com
```

**Did the website load successfully?** (Yes/No): Yes

**Did the CSS styling apply correctly?** (Yes/No): Yes

**Screenshot 5: Working Website**
![Website Live](screenshots/05-website-live.png)

### Error Page Testing

**Test URL used:**
```
http://acton-static-website-francevm-2026.s3-website.eu-central-1.amazonaws.com/nonexistent.html
```

**Did custom error page display?** (Yes/No): Yes

**Screenshot 6: Custom 404 Error Page**
![Error Page](screenshots/06-error-page.png)

---

## Part 6: CLI Commands Used

**Document all AWS CLI commands you executed:**

# Create bucket
francesmacbook@MacBookAir website-files % nano bucket-policy.json

# Enable website hosting
francesmacbook@MacBookAir website-files % aws s3api put-bucket-policy \
  --bucket acton-static-website-francevm-2026 \
  --policy file://bucket-policy.json

# Set bucket policy
francesmacbook@MacBookAir website-files % aws s3api put-bucket-policy \
  --bucket acton-static-website-francevm-2026 \    
  --policy file://bucket-policy.json

---

## Bonus Challenges Completed

- [ ] Challenge 1: Added about.html page
- [ ] Challenge 2: Used subdirectories for organization
- [ ] Challenge 3: Used `aws s3 sync` command

**Bonus Challenge Notes:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

---

## Reflection Questions

### 1. What are the advantages of S3 static hosting compared to traditional web servers?

**Your answer:**
```
1. Cheaper - bandwidth has lower costs
2. Secure
3. Durable
4. Highly scalable
```

### 2. Why is a bucket policy necessary for public website access?

**Your answer:**
```
To protect data being easily accessed by the public. 
```

### 3. What are the limitations of S3 static website hosting?

**Your answer:**
```
Limited scalability and interactivity. It cannot host bigger website needing more features and pages. 
```

### 4. When would you NOT use S3 for website hosting?

**Your answer:**
```
1. When native HTTPS is required as S3 is does not support it
2. When you need frequent content updates. 
3. User efficiency as geographic region affects performance
```

### 5. How does S3 static hosting fit into cost optimization strategies?

**Your answer:**
```
S3 definitely is a no brainer when it comes to cost optimization. With the automated filing system, costs overview are very easy to manage not to mention the prices itself. 
```

---

## Troubleshooting Log

**Did you encounter any issues?** (Yes/No): Yes

**If yes, document the issues and how you resolved them:**

| Issue | Error Message | Solution | Time to Resolve |
|-------|--------------|----------|-----------------|
| I didnt undersrand that I had to create a folder first      | aws: [ERROR]: An error occurred (ParamValidation): Error parsing parameter '--policy': Unable to load paramfile file://bucket-policy.json: [Errno 2] No such file or directory: 'bucket-policy.json'             | created a folder in local         |       10min          |
|       |              |          |                 |
|       |              |          |                 |

---

## Cleanup Confirmation

- [ ] Emptied S3 bucket
- [ ] Deleted S3 bucket
- [ ] Verified no resources remain

**Cleanup CLI commands used:**
```bash
# Empty bucket


# Delete bucket


```

---

## Self-Assessment

**Rate your understanding of each concept (1-5, where 5 is expert):**

| Concept | Rating | Notes |
|---------|--------|-------|
| S3 bucket creation | 5/5 | |
| Static website hosting configuration | 4/5 | |
| Bucket policies and public access | 4/5 | |
| Uploading and managing S3 objects | 5/5 | |
| S3 website endpoints | 5/5 | |
| HTML/CSS basics | 3/5 | |

---

## Instructor Verification

**Instructor Name:** ___________________________

**Date Reviewed:** ___________________________

**Website URL Verified:** ☐ Yes ☐ No

**Comments:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

**Grade/Status:** ___________________________

---

## Additional Resources Referenced

List any documentation, tutorials, or resources you used:

1. ___________________________________________________________
2. ___________________________________________________________
3. ___________________________________________________________

---

**Lab Status:** ☐ Complete ☐ Needs Revision

**Total Time Spent:** ________ minutes

**Submission Date:** ___________________________
