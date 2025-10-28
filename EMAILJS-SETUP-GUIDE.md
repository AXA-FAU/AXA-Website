# EmailJS Setup Guide for AXA Website

This guide will help you set up EmailJS to send automated emails from your contact form.

## Prerequisites

1. An EmailJS account (free at [emailjs.com](https://www.emailjs.com/))
2. Access to your website's `index.html` file

## Step 1: Create EmailJS Account and Service

1. Go to [emailjs.com](https://www.emailjs.com/) and sign up for a free account
2. Once logged in, go to **Email Services** and click **Add New Service**
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the setup instructions for your chosen provider
5. Note down your **Service ID** (e.g., `service_abc123`)

## Step 2: Create Email Template

1. In your EmailJS dashboard, go to **Email Templates**
2. Click **Create New Template**
3. Copy the content from your `email.html` file and paste it into the template editor
4. Set the template name (e.g., "AXA Contact Form")
5. Note down your **Template ID** (e.g., `template_xyz789`)

### Template Variables

Your template should use these variables (already configured in your `email.html`):
- `{{name}}` - Full name from form
- `{{email}}` - Email address from form
- `{{phone}}` - Phone number from form
- `{{company}}` - Company/organization from form
- `{{reason}}` - Reason for contact (General Inquiry, Sponsorship, etc.)
- `{{interest}}` - Grammatically correct interest description
- `{{message}}` - User's message
- `{{personalizedMessage}}` - Context-specific message based on reason

## Step 3: Get Public Key

1. In your EmailJS dashboard, go to **Account** → **General**
2. Find your **Public Key** (e.g., `user_abc123def456`)
3. Copy this key

## Step 4: Configure Your Website

1. Open your `index.html` file
2. Find the `EMAILJS_CONFIG` object (around line 3086)
3. Replace the placeholder value with your actual public key:

```javascript
const EMAILJS_CONFIG = {
    serviceId: 'service_dm4687d',       // ✅ Configured
    templateId: 'template_xwk0afi',     // ✅ Configured
    publicKey: '6wkZG3mn3LOsaa-Jo'      // ✅ Configured
};
```

**🎉 All EmailJS credentials are now fully configured!**

## Step 5: Test the Integration

1. Save your `index.html` file
2. Open your website in a browser
3. Fill out the contact form with test data
4. Submit the form
5. Check that you receive the email at the address you entered

## How It Works

### Form Processing
When someone submits the contact form:

1. **Validation**: The form validates required fields and email format
2. **Content Generation**: The system creates personalized content based on the "Reason for Contact":
   - **General Inquiry**: "learning more about AXA and our space missions"
   - **Sponsorship**: "sponsoring our space missions" 
   - **Partnership**: "forming a partnership with AXA"
   - **Join the Team**: "joining our team"
   - **Media**: "media coverage of our missions"

3. **Email Sending**: EmailJS sends the email to the user's provided email address
4. **Confirmation**: User sees a success message and the form resets

### Email Content
The email includes:
- Personalized greeting using the user's first name
- Context-specific message based on their reason for contact
- Summary of their form submission (including company information)
- Professional AXA branding

## Troubleshooting

### Common Issues

1. **"EmailJS not configured" error**
   - All EmailJS credentials are now configured ✅
   - Service ID: `service_dm4687d` ✅
   - Template ID: `template_xwk0afi` ✅  
   - Public Key: `6wkZG3mn3LOsaa-Jo` ✅

2. **Email not sending**
   - Check your email service configuration in EmailJS dashboard
   - Verify your email provider settings (Gmail, Outlook, etc.)
   - Check browser console for error messages

3. **Template variables not working**
   - Ensure your EmailJS template uses the exact variable names from the code
   - Check that the template is published in your EmailJS dashboard

### Testing Tips

- Use a real email address for testing
- Check spam folder if emails don't arrive
- Test with different "Reason for Contact" options to see personalized messages
- Use browser developer tools to check for JavaScript errors

## Security Notes

- Your Public Key is safe to use in client-side code
- EmailJS handles the actual email sending securely
- No sensitive credentials are exposed in your website code
- The free plan includes 200 emails per month

## Support

If you need help:
1. Check the [EmailJS documentation](https://www.emailjs.com/docs/)
2. Review the browser console for error messages
3. Test with a simple template first to verify basic functionality

## Next Steps

Once everything is working:
1. Consider upgrading to a paid EmailJS plan for more emails
2. Add additional form fields if needed (company, website, etc.)
3. Customize the email template further to match your brand
4. Set up email analytics to track form submissions
