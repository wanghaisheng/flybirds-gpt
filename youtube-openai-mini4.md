# input

You are an AI and automation testing expert. Your task is to design a detailed test plan for the {{FUNCTION_NAME}} functionality of a given website or app. Follow these instructions carefully to create a comprehensive and structured test plan.

1. The website or app you will be testing is:
<website_or_app>
{{WEBSITE_OR_APP}}
</website_or_app>

2. Create a step-by-step test plan for the {{FUNCTION_NAME}} functionality. Include the following steps, expanding on each with specific actions and checks:

a. Access the website or open the app
b. Verify successful loading of the page or app
c. Locate the {{FUNCTION_NAME}} feature
d. Verify the {{FUNCTION_NAME}} feature is accessible and functioning
e. Perform necessary actions to test the {{FUNCTION_NAME}} functionality
f. Verify the expected outcome of using the {{FUNCTION_NAME}} feature

3. For each step, provide:
   - The action to be performed
   - What to check or verify
   - Potential issues to look out for
   - Any additional relevant details

4. Consider various scenarios and edge cases related to the {{FUNCTION_NAME}} functionality, such as:
   - Different user roles or permissions
   - Various input types or formats
   - Error handling and validation
   - Performance under different conditions

5. Include any necessary setup or preconditions for testing the {{FUNCTION_NAME}} functionality.

6. Suggest tools or methods that could be used to automate parts of this test plan.

Present your test plan in a clear, structured format. Use numbered steps for the main test flow and bullet points for details within each step. Enclose your entire test plan within <test_plan> tags.

Begin your response with "Here is a detailed test plan for the {{FUNCTION_NAME}} functionality of {{WEBSITE_OR_APP}}:" and then provide the test plan.

## result

Here is a detailed test plan for the video upload functionality of youtube.com:
<test_plan>
Setup and Preconditions:

Ensure you have a valid YouTube account
Prepare various video files for testing (different formats, sizes, and lengths)
Have a stable internet connection

Test Plan:

Access the website

Open a web browser and navigate to youtube.com
Check: Page loads correctly and quickly
Potential issues: Slow loading, error messages, or security warnings


Verify successful loading of the page

Check: All elements are visible and properly aligned
Check: No broken images or missing content
Potential issues: Layout issues on different browsers or devices


Locate the video upload feature

Look for the upload button (usually a camera icon with a plus sign)
Check: The upload button is visible and clickable
Potential issues: Button not visible for certain user roles or on mobile devices


Verify the video upload feature is accessible and functioning

Click on the upload button
Check: The upload interface opens correctly
Potential issues: Pop-up blockers preventing the interface from opening


Perform necessary actions to test the video upload functionality
a. Select a video file

Click "Select files" or drag and drop a video file
Check: File selection dialog opens or drag-and-drop works
Potential issues: Certain file types not recognized or too large files rejected

b. Upload process

Observe the upload progress bar
Check: Upload starts and progress is shown accurately
Potential issues: Slow upload speeds, connection interruptions, or upload failures

c. Video processing

Wait for YouTube to process the video
Check: Processing status is displayed and updates in real-time
Potential issues: Long processing times or processing failures

d. Add video details

Fill in title, description, tags, and other metadata
Check: All input fields are editable and save correctly
Potential issues: Character limits, special character handling, or save failures

e. Set video privacy settings

Choose between Public, Unlisted, or Private
Check: Privacy settings are applied correctly
Potential issues: Settings not saving or incorrect default settings

f. Monetization and age restrictions (if applicable)

Set monetization preferences and age restrictions
Check: Options are available and can be selected
Potential issues: Options not appearing for certain account types

g. Publish the video

Click the "Publish" or "Save" button
Check: Video is successfully published and appears in the channel
Potential issues: Publish failures or delays in video appearing


Verify the expected outcome of using the video upload feature

Navigate to the channel page or video management section
Check: Newly uploaded video is listed and playable
Check: Video details and settings match what was input
Potential issues: Video not appearing, incorrect details, or playback issues



Additional Scenarios to Test:

Upload videos of various formats (MP4, AVI, MOV, etc.)
Test with extremely short and very long videos
Attempt to upload files exceeding YouTube's size limits
Test uploads with poor internet connectivity
Verify upload functionality for different user roles (new users, established creators)
Test upload feature on mobile devices and different browsers
Attempt concurrent uploads of multiple videos
Test cancellation of uploads midway through the process

Automation Suggestions:

Use Selenium WebDriver for automating browser interactions and file uploads
Implement API testing for direct video uploads and metadata updates
Use BrowserStack or similar services for cross-browser and device testing
Implement performance testing tools like JMeter for load testing the upload feature
Use mock objects to simulate various network conditions and server responses
Implement visual regression testing tools for UI consistency checks

</test_plan>
