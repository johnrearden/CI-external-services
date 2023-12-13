# AWS Bucket Setup

## Outline
There are two separate procedures that we need to run through here. 

1: We need to create a new S3 bucket to store our static and media files.

2: We need to set up Identity and Access Management (IAM), so that we can gain
programmatic access to our bucket, in order for our Django app to be able to upload to our bucket.

### Step 1 - Set up the bucket

1:  Create a new bucket in S3

2:  Click ACLs enabled (bucket owner preferred)

3:  Uncheck the Block All Public Access checkbox

4:  Click on 'Create Bucket'

5:  Click on your new bucket in the bucket list

6:  On the Properties tab, scroll to the bottom. The last panel is Static Website Hosting. 
- Click Edit
- Click Enable.
- Fill in values for the index and error documents. Use the names suggested by the 
       placeholder text.
- Click Save Changes.

7:  On the permissions tab, scroll down to the CORS panel. Paste in this configuration -

```
[
  {
      "AllowedHeaders": [
          "Authorization"
      ],
      "AllowedMethods": [
          "GET"
      ],
      "AllowedOrigins": [
          "*"
      ],
      "ExposeHeaders": []
  }
]
```

8:  Scroll to the Bucket Policy tab, and click Edit. Then click Policy Generator.
- In the Step 1 box, select 'S3 Bucket Policy'
- In the Add Statement(s) box, enter '*' in the Principals input.
- Click the Actions select box. Scroll down, and check only the 'Get Object'
  option.
- The ARN can be found on the previous tab (Edit Bucket Policy) - it should 
  still be open in your browser. Copy and paste it into the ARN input.
- Click Add Statement, and then Generate Policy (this button should appear upon clicking Add Statement)
- You'll be shown the generated policy, which you'll need to copy and paste into the Bucket Policy Editor, which is on the previously opened tab.
- Add '/*' to the end of the "Resource" key.
- Click Save Changes

9: Scroll to the Access Control List panel, and click Edit. 
- Under 'Everyone (public access)', click the List button
- Check the acknowledgement box at the bottom of the screen.
- Click Save Changes.

### Step 2 - Set up IAM for programmatic access to the bucket
In this second step, we're going to perform 3 actions. We need to create a group for 
our users first. Then we'll create a group policy to let members of the group access the S3 bucket created above. Finally, we'll create a user and add them to the group.

1:  In the sidebar, under Access Groups, click User Groups.

2:  Click Create Group

3:  Give your group a name, and then scroll to the bottom and click the Create Group button.

4:  In the sidebar, again under Access Groups, click Policies, and then the Create Policy button.

5:  Click the JSON button.

6:  Enter S3 in the Choose a Service input, and select the All Actions checkbox.

7:  Copy the bucket ARN (which can be found on the Properties tab of your bucket settings
in S3), and paste it, within quotes, into the Resources list.

8:  Click Next.

9:  Give your policy a name and a description.

10: Click Create Policy.

11: Now, in the sidebar again, click User Groups, and then the Permissions tab.

12: Click Add Permissions, and in the dropdown menu, select Attach Policies.

13: In the Other Permissions Policies input, enter your policy name. Click the checkbox, 
and then click Attach Policies.

14: In the sidebar, click Users, and Create User. Enter a name, and click Next.

15: Make sure the Add User to Group radio button is selected, click the checkbox for your
new User Group, and click Next.

16: Click Create User, and then select your new User from the list.

17: Click on the Security Credentials tab. Scroll to Access Keys, and click Create Access Key. Click Application Running Outside AWS, and then the Next button.

18: Leave the Description Tag Value blank, and click Create Access Key.

19: At the bottom of the screen, before clicking Done, hit the Download .csv File button.

20: Keep this safe, it contains your Access Key, and Secret Access Key, which you will need to add to your Django environment variables, and your Heroku config vars.