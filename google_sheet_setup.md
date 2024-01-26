# Steps to activate Google Sheet API creds

### 1 - Go to the [Google Cloud Console](https://console.cloud.google.com/home)

### 2 - Click on the team dropdown

![team dropdown](/screenshots/google_sheet/shot1.png)

### 3 - Create new project

![new project](/screenshots/google_sheet/shot2_name_the_project.png)

### 4 - Navigate to API library

![api library](/screenshots/google_sheet/shot3_nav_to_api_library.png)

### 5 - Type in 'Google Drive'.

![google drive](/screenshots/google_sheet/shot4_select_google_drive_api.png)

### 6 - Select own project. 

### 7 - Enable API.

![enable api](/screenshots/google_sheet/shot6_enable_api.png)

### 8 - Create credentials.

![create credentials](/screenshots/google_sheet/shot7_create_credentials.png)

### 9 - Enter a service account name. Click Next.

### 10 - Set role to Editor. Click Next.

### 11 - Leave options blank, click Done.

![service account](/screenshots/google_sheet/shot10_done.png)

### 12 - Click Credentials tab and click your new service account.

![click credentials](/screenshots/google_sheet/shot11_click_credentials_and_service_ac.png)

### 13 - Click 'Keys' tab.

![keys](/screenshots/google_sheet/shot12_click_keys.png)

### 14 - Click 'Add Key'.

![add key](/screenshots/google_sheet/shot13_add_key_button.png)

### 15 - Create JSON key.

![create json](/screenshots/google_sheet/shot14_create_json_key.png)

### 16 - Your credentials should be in your downloads folder.
![in downloads](/screenshots/google_sheet/shot15_key_should_be_in_downloads.png)


# Enable Google Sheets API
### 1 - Find the Google Sheets API
![find api](/screenshots/google_sheet/shot_a_google_sheets_api.png)

### 3 - Click Enable
![click enable](/screenshots/google_sheet/shot_b_enable.png)


# Finally - 
### Grab the client email variable from your creds.json file, open your worksheet, click Share, and paste it in.
![share with client email](/screenshots/google_sheet/shot_c_share_sheet_with_client_email.png)
### Select editor in the dropdown, uncheck Notify people, and click Share.