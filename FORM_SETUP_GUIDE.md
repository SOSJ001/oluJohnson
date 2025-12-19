# Form Submission Setup Guide

The License Renewal form is now ready to collect data. This guide shows you how to set up **Google Sheets integration** (no redirects, users stay on your site).

---

## Option 1: Google Sheets via Apps Script (Recommended)

✅ **Users stay on your site** (no redirect)  
✅ **Unlimited submissions** (completely free)  
✅ **Data stored in Google Sheets** (easy to view/manage)  
✅ **Professional appearance** (seamless integration)  
✅ **No package installation needed**  
✅ **Real-time data** (appears instantly in Sheets)

### Step-by-Step Setup

#### Step 1: Create a Google Sheet

1. Go to [Google Sheets](https://sheets.google.com/)
2. Create a new spreadsheet
3. Name it "Tasmal X License Renewals" (or any name you prefer)
4. In the first row, add these column headers:
   ```
   Timestamp | Organization | Primary Contact | Physical Address | Email | Phone | Serial Number | Hardware ID | Operating System | Installation Site | License Term | Current License | License Start Date | License Expiration Date | Additional Notes
   ```
5. Save the spreadsheet

#### Step 2: Create Google Apps Script

1. In your Google Sheet, click **Extensions** → **Apps Script**
2. Delete any existing code
3. Copy and paste this code:

```javascript
function doPost(e) {
	try {
		// Get the active spreadsheet
		const sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();

		// Parse the JSON data from the form
		const data = JSON.parse(e.postData.contents);

		// Get current timestamp
		const timestamp = new Date();

		// Add the data to the sheet
		sheet.appendRow([
			timestamp,
			data.organization || '',
			data.primaryContact || '',
			data.physicalAddress || '',
			data.email || '',
			data.phone || '',
			data.serialNumber || '',
			data.hardwareId || '',
			data.operatingSystem || '',
			data.installationSite || '',
			data.licenseTerm || '',
			data.currentLicense || 'Not provided',
			data.currentLicenseStartDate || 'Not provided',
			data.currentLicenseExpirationDate || 'Not provided',
			data.additionalNotes || 'None'
		]);

		// Return success response
		return ContentService.createTextOutput(
			JSON.stringify({
				success: true,
				message: 'Data saved successfully'
			})
		).setMimeType(ContentService.MimeType.JSON);
	} catch (error) {
		// Return error response
		return ContentService.createTextOutput(
			JSON.stringify({
				success: false,
				error: error.toString()
			})
		).setMimeType(ContentService.MimeType.JSON);
	}
}

// Optional: Test function (you can run this to test)
function test() {
	const testData = {
		organization: 'Test Organization',
		primaryContact: 'John Doe, IT Manager',
		physicalAddress: '123 Main St, City, Country',
		email: 'test@example.com',
		phone: '+1234567890',
		serialNumber: 'TEST123',
		hardwareId: 'HW456',
		operatingSystem: 'Windows 11 Pro',
		installationSite: 'Main Branch',
		licenseTerm: '2',
		currentLicense: 'LIC789',
		currentLicenseStartDate: '2024-01-01',
		currentLicenseExpirationDate: '2025-12-31',
		additionalNotes: 'This is a test'
	};

	const mockEvent = {
		postData: {
			contents: JSON.stringify(testData)
		}
	};

	doPost(mockEvent);
}
```

4. Click **Save** (💾 icon) or press `Ctrl+S` / `Cmd+S`
5. Name your project: "Tasmal X Form Handler" (or any name)

#### Step 3: Deploy as Web App

1. Click **Deploy** → **New deployment**
2. Click the gear icon ⚙️ next to "Select type" → Choose **Web app**
3. Fill in the deployment settings:
   - **Description**: "Tasmal X License Renewal Form Handler"
   - **Execute as**: "Me" (your email)
   - **Who has access**: **"Anyone"** (important!)
4. Click **Deploy**
5. **Copy the Web App URL** - it will look like:
   ```
   https://script.google.com/macros/s/AKfycby.../exec
   ```
   ⚠️ **Save this URL - you'll need it!**

#### Step 4: Authorize the Script

1. After deploying, you'll see an "Authorization required" message
2. Click **Authorize access**
3. Choose your Google account
4. Click **Advanced** → **Go to [Project Name] (unsafe)**
5. Click **Allow** to grant permissions
6. You may need to deploy again after authorization

#### Step 5: Update Your Environment Variable

1. Open the `.env` file in your project root (if it doesn't exist, copy `.env.example` to `.env`)
2. Find this line:
   ```
   PUBLIC_GOOGLE_SHEETS_WEB_APP_URL=YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL
   ```
3. Replace `YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL` with your Web App URL:
   ```
   PUBLIC_GOOGLE_SHEETS_WEB_APP_URL=https://script.google.com/macros/s/AKfycby.../exec
   ```
4. Save the `.env` file
5. **Important:**
   - The `.env` file is gitignored (won't be committed to version control)
   - Restart your dev server if it's running (`npm run dev`)
   - For production, set this environment variable in your hosting platform

#### Step 6: Enable Google Sheets Integration in Code

The code is already set up to use the environment variable! Once you've added the URL to `.env`, the form will automatically use Google Sheets when you submit it. No code changes needed - just restart your dev server.

```javascript
// Option 1: Google Sheets via Apps Script (RECOMMENDED)
const response = await fetch(GOOGLE_SHEETS_WEB_APP_URL, {
	method: 'POST',
	mode: 'no-cors',
	headers: {
		'Content-Type': 'application/json'
	},
	body: JSON.stringify({
		organization: data.organization,
		primaryContact: data.primaryContact,
		physicalAddress: data.physicalAddress,
		email: data.email,
		phone: data.phone,
		serialNumber: data.serialNumber,
		hardwareId: data.hardwareId,
		operatingSystem: data.operatingSystem,
		installationSite: data.installationSite,
		licenseTerm: data.licenseTerm,
		currentLicense: data.currentLicense,
		currentLicenseStartDate: data.currentLicenseStartDate,
		currentLicenseExpirationDate: data.currentLicenseExpirationDate,
		additionalNotes: data.additionalNotes,
		timestamp: new Date().toISOString()
	})
});
```

**Note:** The code automatically uses Google Sheets if the environment variable is set. If not set, it falls back to mailto.

#### Step 7: Test It!

1. Fill out the form on your website
2. Submit it
3. Check your Google Sheet - the data should appear immediately!
4. Each submission will add a new row with all the form data

#### Optional: Email Notifications

Want to receive an email notification every time someone submits the form? Here's how to set it up:

**Step 1: Open Your Apps Script**

1. Go to your Google Sheet
2. Click **Extensions** → **Apps Script**
3. You should see your existing `doPost` function

**Step 2: Add Email Notification Code**

Find this line in your `doPost` function:

```javascript
sheet.appendRow([...]);
```

Right **after** that line (but before the `return` statement), add this code:

```javascript
// Send email notification (with error handling)
try {
	console.log('Attempting to send email notification...');
	const emailBody = `
New Tasmal X License Renewal Request

Organization: ${data.organization || 'Not provided'}
Primary Contact: ${data.primaryContact || 'Not provided'}
Physical Address: ${data.physicalAddress || 'Not provided'}
Email: ${data.email || 'Not provided'}
Phone: ${data.phone || 'Not provided'}

Hardware Information:
- Serial Number: ${data.serialNumber || 'Not provided'}
- Hardware ID: ${data.hardwareId || 'Not provided'}
- Operating System: ${data.operatingSystem || 'Not provided'}
- Installation Site: ${data.installationSite || 'Not provided'}

License Details:
- Requested Term: ${data.licenseTerm || 'Not provided'} year(s)
- Current License: ${data.currentLicense || 'Not provided'}
- Start Date: ${data.currentLicenseStartDate || 'Not provided'}
- Expiration Date: ${data.currentLicenseExpirationDate || 'Not provided'}

Additional Notes: ${data.additionalNotes || 'None'}
			`;

	MailApp.sendEmail({
		to: 'service.engineer@olujohnsonbusinesstechnicalservices.com',
		subject: 'New Tasmal X License Renewal Request',
		body: emailBody
	});
	console.log('Email sent successfully');
} catch (emailError) {
	// Log email error but don't fail the form submission
	console.error('Email sending failed:', emailError.toString());
	console.error('Error details:', emailError);
}
```

**Step 3: Update Email Address (if needed)**

Change the email address in the code:

```javascript
to: 'your-email@example.com',  // Replace with your email
```

**Step 4: Save and Redeploy**

1. Click **Save** (💾 icon) or press `Ctrl+S` / `Cmd+S`
2. Click **Deploy** → **Manage deployments**
3. Click the pencil icon ✏️ next to your deployment
4. Click **Deploy** (this creates a new version)
5. **Important:** You may need to authorize the script again for email permissions

**Step 5: Authorize Email Permissions**

**Option A: If Authorization Prompt Appears**

1. After redeploying, you'll see an "Authorization required" message
2. Click **Authorize access**
3. Review the permissions - it will ask for access to:
   - Google Sheets (to write data)
   - Gmail (to send emails)
4. Click **Allow** to grant permissions

**Option B: If Authorization Prompt Doesn't Appear (Manual Authorization)**

If the prompt doesn't appear after redeploying, manually trigger authorization:

1. **Method 1: Review Permissions**

   - In Apps Script, look for a **lock icon** 🔒 or **"Review permissions"** button
   - Click it to review and authorize permissions
   - Or go to **View** → **Show manifest file** → Look for authorization settings

2. **Method 2: Run a Test Function**

   - Add this test function to your script:

   ```javascript
   function testEmailAuth() {
   	MailApp.sendEmail({
   		to: 'your-email@example.com',
   		subject: 'Test',
   		body: 'Test'
   	});
   }
   ```

   - Click **Run** → Select `testEmailAuth`
   - This will trigger the authorization prompt
   - Click **Review permissions** → **Allow**

3. **Method 3: Revoke and Re-authorize**

   - Go to [Google Account Permissions](https://myaccount.google.com/permissions)
   - Find your Apps Script project (e.g., "Tasmal X Form Handler")
   - Click **Remove access** or the trash icon
   - Go back to Apps Script and redeploy
   - The authorization prompt should appear

4. **Verify Permissions Were Granted**
   - After authorizing, test the email function (Method 2 above)
   - If it works, permissions are set correctly

**Step 6: Test It!**

1. Submit a test form on your website
2. Check your email inbox - you should receive a notification
3. Check your Google Sheet - the data should still be saved

**Complete Code Example:**

Here's what your `doPost` function should look like with email notifications:

```javascript
function doPost(e) {
	try {
		// Get the active spreadsheet
		const sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();

		// Parse the JSON data from the form
		const data = JSON.parse(e.postData.contents);

		// Get current timestamp
		const timestamp = new Date();

		// Add the data to the sheet
		sheet.appendRow([
			timestamp,
			data.organization || '',
			data.primaryContact || '',
			data.physicalAddress || '',
			data.email || '',
			data.phone || '',
			data.serialNumber || '',
			data.hardwareId || '',
			data.operatingSystem || '',
			data.installationSite || '',
			data.licenseTerm || '',
			data.currentLicense || 'Not provided',
			data.currentLicenseStartDate || 'Not provided',
			data.currentLicenseExpirationDate || 'Not provided',
			data.additionalNotes || 'None'
		]);

		// Send email notification
		const emailBody = `
New Tasmal X License Renewal Request

Organization: ${data.organization}
Primary Contact: ${data.primaryContact}
Physical Address: ${data.physicalAddress}
Email: ${data.email}
Phone: ${data.phone}

Hardware Information:
- Serial Number: ${data.serialNumber}
- Hardware ID: ${data.hardwareId}
- Operating System: ${data.operatingSystem}
- Installation Site: ${data.installationSite}

License Details:
- Requested Term: ${data.licenseTerm} year(s)
- Current License: ${data.currentLicense}
- Start Date: ${data.currentLicenseStartDate}
- Expiration Date: ${data.currentLicenseExpirationDate}

Additional Notes: ${data.additionalNotes}
		`;

		// Option 1: Using MailApp (works with any email provider)
		// Send email with better deliverability settings
		MailApp.sendEmail({
			to: 'service.engineer@olujohnsonbusinesstechnicalservices.com',
			subject: 'New Tasmal X License Renewal Request',
			body: emailBody,
			replyTo: data.email, // Use the form submitter's email as reply-to
			name: 'Tasmal X License System' // Sender name (if supported)
		});

		// Option 2: Using GmailApp (Gmail accounts only - sometimes works better)
		// Uncomment this and comment out MailApp above if MailApp doesn't work
		// GmailApp.sendEmail(
		// 	'service.engineer@olujohnsonbusinesstechnicalservices.com',
		// 	'New Tasmal X License Renewal Request',
		// 	emailBody
		// );

		// Return success response
		return ContentService.createTextOutput(
			JSON.stringify({
				success: true,
				message: 'Data saved successfully'
			})
		).setMimeType(ContentService.MimeType.JSON);
	} catch (error) {
		// Return error response
		return ContentService.createTextOutput(
			JSON.stringify({
				success: false,
				error: error.toString()
			})
		).setMimeType(ContentService.MimeType.JSON);
	}
}
```

**Troubleshooting Email Notifications:**

- **Not receiving emails? Follow these steps:**

  1. **Check the Apps Script Execution Log:**

     - In Apps Script, go to **View** → **Execution log**
     - Look for any errors when the form was submitted
     - If you see errors, they'll tell you what went wrong

  2. **Verify Email Code Was Added:**

     - Make sure the email code is placed **after** `sheet.appendRow([...])` but **before** the `return` statement
     - Check that there are no syntax errors (missing quotes, brackets, etc.)

  3. **Check Gmail Permissions:**

     - After adding email code, you **must redeploy** the script
     - **If the authorization prompt doesn't appear**, you need to manually authorize:
       1. In Apps Script, click the **lock icon** 🔒 (or **View** → **Show manifest file**)
       2. Click **Review permissions**
       3. Choose your Google account
       4. Click **Advanced** → **Go to [Project Name] (unsafe)**
       5. Click **Allow** to grant Gmail permissions
     - Alternatively, you can revoke and re-authorize:
       1. Go to [Google Account Permissions](https://myaccount.google.com/permissions)
       2. Find your Apps Script project
       3. Click **Remove access**
       4. Redeploy your script - it will ask for permissions again
     - Make sure you clicked **Allow** for Gmail access
     - If you didn't authorize, the email won't send

  4. **Redeploy After Adding Email Code:**

     - **Deploy** → **Manage deployments**
     - Click the pencil icon ✏️ to edit
     - Click **Deploy** (creates new version)
     - **Authorize** when prompted

  5. **Check Your Spam/Junk Folder:**

     - Emails from Apps Script sometimes go to spam
     - Check your spam folder

  6. **Verify Email Address:**

     - Make sure the email address in the code is correct
     - No typos or extra spaces

  7. **Test the Email Function:**

     - In Apps Script, create a simple test function:

     ```javascript
     function testEmailAuth() {
     	MailApp.sendEmail({
     		to: 'your-email@example.com',
     		subject: 'Test Email',
     		body: 'This is a test'
     	});
     }
     ```

     - **Important Steps:**
       1. Click **Run** → Select `testEmailAuth` from the dropdown
       2. **If you see "Authorization required"** → Click **Review permissions**
       3. Choose your Google account
       4. Click **Advanced** → **Go to [Project Name] (unsafe)**
       5. Click **Allow** to grant Gmail permissions
       6. Run the function again - it should work now
     - **If you get an error**, check the execution log:
       - Go to **View** → **Execution log**
       - Look for the error message
       - Common errors:
         - "Exception: Access denied" → Permissions not granted
         - "Exception: Invalid email" → Check email address format
         - "Exception: Service invoked too many times" → Quota limit reached
     - If this works, the issue is with the form submission
     - If this doesn't work, Gmail permissions are not authorized

  8. **Check for Errors in the Code:**

     - Make sure the email code is inside the `try` block
     - If there's an error, it should be caught and logged
     - Check the execution log for specific error messages

  9. **Common Issues:**

     - **Email code not executed:** Make sure it's after `sheet.appendRow` but before `return`
     - **Permissions not granted:**
       - Run the test function from the Apps Script editor (not just deploy)
       - When you run it, it will prompt for authorization
       - You MUST click "Review permissions" → "Allow" when prompted
       - If no prompt appears, revoke access and try again
     - **Script not redeployed:** Changes won't work until you redeploy
     - **Email in spam:** Check spam folder
     - **Syntax error:** Check for missing quotes, brackets, or commas
     - **"Access denied" error:** Gmail permissions not authorized - run test function to trigger authorization
     - **Quota exceeded:** Google has daily email limits - wait 24 hours or check quota usage

  10. **Test Function Works But doPost Email Doesn't? (Common Issue):**

      If `testEmailAuth()` works but emails from `doPost` don't send:

      **A. Check if Email Code is in Deployed Version:**

      - Make sure you saved the script after adding email code
      - **You MUST redeploy** after adding email code:
        1. **Deploy** → **Manage deployments**
        2. Click the pencil icon ✏️
        3. Click **Deploy** (creates new version)
      - The deployed version might be using old code without email

      **B. Check Execution Log for doPost:**

      - Submit a form on your website
      - Go to **View** → **Execution log**
      - Look for the `doPost` execution
      - Check for error messages
      - If you see "Attempting to send email notification..." but no "Email sent successfully", the email failed

      **C. Verify Email Code Placement:**

      - Email code should be AFTER `sheet.appendRow([...])`
      - Email code should be BEFORE the `return` statement
      - Email code should be INSIDE the `try` block

      **D. Check for Variable Issues:**

      - Make sure `data.email` and other variables exist
      - Add `|| 'Not provided'` fallbacks to prevent undefined errors
      - Check the execution log for any variable-related errors

      **E. Add Better Logging:**

      - Add `console.log('Attempting to send email notification...');` before email
      - Add `console.log('Email sent successfully');` after email
      - This helps identify where it's failing

  11. **Code Runs But Email Not Sending? (You see "Attempting to send email..." in log):**

      This means the code is executing but `MailApp.sendEmail()` is failing. Try these:

      **A. Check for Error Messages:**

      - Add this after `MailApp.sendEmail()`:

      ```javascript
      console.log('Email sent successfully');
      ```

      - If you DON'T see this message in the log, the email failed
      - Check the execution log for any error messages after "Attempting to send email..."

      **B. Verify Gmail Permissions Are Actually Granted:**

      - Go to [Google Account Permissions](https://myaccount.google.com/permissions)
      - Find your Apps Script project
      - Check if Gmail permissions are listed
      - If not, revoke and re-authorize:
        1. Remove access
        2. Run `testEmailAuth` function again
        3. Click "Review permissions" → "Allow"

      **C. Check Email Quota:**

      - Google Apps Script has daily email limits
      - Free accounts: 100 emails/day
      - If you've exceeded the limit, wait 24 hours
      - Check quota: The error would say "Service invoked too many times"

      **D. Verify Email Address:**

      - Make sure the email address is correct
      - No typos or extra spaces
      - Try sending to a different email to test

      **E. Add Better Error Handling:**

      - Wrap the email code in try-catch (already in the code example)
      - Check the execution log for the actual error message
      - The error will tell you exactly what's wrong

  12. **Email Code Not Executing? Check These:**

      - **Is the email code in the deployed version?**

        - Make sure you saved the script after adding email code
        - **You MUST redeploy** after adding email code:
          1. **Deploy** → **Manage deployments**
          2. Click the pencil icon ✏️
          3. Click **Deploy** (creates new version)
        - The deployed version might be using old code without email

      - **Add logging to verify email code runs:**

        - Add this before the email code to verify it's reached:

        ```javascript
        // Add this line before MailApp.sendEmail
        console.log('Attempting to send email...');
        ```

        - Check the execution log - if you see "Attempting to send email...", the code is running
        - If you don't see it, the email code isn't being executed

      - **Check if email code is in the right place:**
        - It should be AFTER `sheet.appendRow([...])`
        - It should be BEFORE the `return` statement
        - It should be INSIDE the `try` block

  13. **Still Not Working? Try This Complete Reset:**

      **Step 1: Check Execution Log**

      - In Apps Script: **View** → **Execution log**
      - Look for `testEmailAuth` execution
      - What error message do you see?
      - Common errors:
        - `Exception: Access denied` = Permissions not granted
        - `Exception: Invalid email` = Email format issue
        - `Exception: Service invoked too many times` = Quota limit

      **Step 2: Complete Permission Reset**

      1. Go to [Google Account Permissions](https://myaccount.google.com/permissions)
      2. Find your Apps Script project (search for "Tasmal" or "Apps Script")
      3. Click **Remove access** (trash icon) for ALL Apps Script entries
      4. Go back to Apps Script editor
      5. Click **Run** → Select `testEmailAuth`
      6. **You should now see "Authorization required"**
      7. Click **Review permissions**
      8. Choose your Google account
      9. Click **Advanced** → **Go to [Project Name] (unsafe)**
      10. Click **Allow**
      11. Run `testEmailAuth` again - it should work now

      **Step 3: Verify It Works**

      - After authorizing, run `testEmailAuth` again
      - Check your email inbox (and spam folder)
      - If you receive the email, permissions are working!

      **Step 4: If Still Not Working**

      - Make sure you're using the same Google account in Apps Script that owns the email
      - Check if your Google account has 2FA enabled (shouldn't block this, but worth checking)
      - Try a different email address to rule out email-specific issues
      - Check Apps Script quota: **View** → **Execution log** → Look for quota errors

- **Want to send to multiple emails?**

  - Use a comma-separated list: `to: 'email1@example.com, email2@example.com'`

- **Want HTML email instead of plain text?**

  - Use `htmlBody` instead of `body` in the `MailApp.sendEmail()` call

- **Emails going to spam folder? Try these fixes:**

  - **Use a professional subject line:**

    - Avoid words like "Test", "Free", "Urgent", "Click here"
    - Use clear, professional subjects like "Tasmal X License Renewal Request"

  - **Add reply-to address:**

    ```javascript
    MailApp.sendEmail({
    	to: 'service.engineer@olujohnsonbusinesstechnicalservices.com',
    	subject: 'New Tasmal X License Renewal Request',
    	body: emailBody,
    	replyTo: data.email // Use form submitter's email
    });
    ```

  - **Use GmailApp instead (often better deliverability):**

    ```javascript
    GmailApp.sendEmail(
    	'service.engineer@olujohnsonbusinesstechnicalservices.com',
    	'New Tasmal X License Renewal Request',
    	emailBody,
    	{
    		replyTo: data.email,
    		name: 'Tasmal X License System'
    	}
    );
    ```

  - **Make email content professional:**

    - Avoid excessive exclamation marks
    - Use proper formatting
    - Include company name and contact info

  - **Whitelist the sender:**

    - Ask recipients to add the sender email to their contacts
    - Mark the first email as "Not Spam" in Gmail

  - **Note:** Some spam filtering is unavoidable, but these steps help

- **MailApp not working? Try GmailApp instead:**

  - If `MailApp.sendEmail()` isn't working, try `GmailApp.sendEmail()` instead
  - `GmailApp` is specifically for Gmail accounts and sometimes works better
  - **Syntax difference:**

    ```javascript
    // MailApp (object syntax)
    MailApp.sendEmail({
    	to: 'email@example.com',
    	subject: 'Subject',
    	body: 'Body'
    });

    // GmailApp (parameter syntax)
    GmailApp.sendEmail(
    	'email@example.com', // to
    	'Subject', // subject
    	'Body' // body
    );
    ```

  - **Important:** `GmailApp` only works with Gmail accounts
  - You'll still need to authorize Gmail permissions
  - Replace `MailApp` with `GmailApp` in your code if `MailApp` isn't working

- **Want to add error handling for emails?**
  - Wrap the email code in a try-catch to prevent form submission from failing if email fails:
  ```javascript
  try {
    MailApp.sendEmail({...});
  } catch (emailError) {
    // Email failed but form submission continues
    console.error('Email error:', emailError);
  }
  ```

---

## Current Implementation (Fallback)

Right now, the form uses a **mailto fallback** that opens the user's email client. This works but isn't ideal for production.

**To use Google Sheets**, follow the steps above and update the code accordingly.

---

## Troubleshooting

### Data not appearing in Sheets?

- Make sure you authorized the script
- Check that "Who has access" is set to "Anyone"
- Verify the Web App URL is correct
- Check the Apps Script execution log (View → Execution log)

### Getting errors?

- Make sure column headers match exactly
- Check that the sheet is the active one
- Verify the JSON data structure matches

### Need to update the script?

- Make changes in Apps Script editor
- Click **Deploy** → **Manage deployments**
- Click the pencil icon ✏️ to edit
- Click **Deploy** again (creates new version)

---

## Security Note

The Web App URL is public, but that's okay because:

- It only accepts POST requests with specific data structure
- It only writes to your specific sheet
- You can add validation/rate limiting if needed

For extra security, you can add a simple password check in the script.

---

## Testing

After setup:

1. Fill out the form on your website
2. Submit it
3. Check your Google Sheet - the data should appear immediately!
4. Verify all data is captured correctly
