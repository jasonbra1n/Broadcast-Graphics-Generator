Create a professional, single-file React web application using Tailwind CSS that functions as a Broadcast Graphics Generator for use with Blackmagic ATEM Mini switchers.

**The application must include the following features and technical specifications:**

**Layout:**

*   A responsive two-column layout: a left sidebar for controls and a main area for the live preview.
*   The live preview area must maintain a 16:9 aspect ratio (1920x1080 display space).

**Templates:**

*   Implement state for four distinct template types:
    *   `lowerThird` (Two lines of text, typically name and title).
    *   `bug` (Single line of text, e.g., "LIVE" or a logo placeholder, positioned in a corner).
    *   `ticker` (Breaking news style bar with a colored label and scrolling text area).
    *   `slate` (Full-screen overlay for "Up Next" messages).

**Controls (Sidebar):**

*   Text inputs for two lines of text (`text1` and `text2`).
*   Color pickers for `primaryColor` (accents/main bars) and `secondaryColor` (backgrounds/secondary bars).
*   Font selection (e.g., Inter, Roboto, Oswald).
*   Range sliders to control global graphic position (`posX` and `posY`, 0-100% relative to the 16:9 canvas) and scale (50-200%).
*   Buttons for selecting the four templates.

**Preview Functionality:**

*   The main area must display the graphic in real-time using DOM/JSX elements based on the state.
*   Include a toggle button to switch the background of the preview between:
    *   A photo placeholder (simulating live video feed).
    *   A chessboard pattern (simulating the transparency/alpha channel).

**Download Functionality (Crucial):**

*   Implement a "Download PNG" button that triggers a process to create and download the final graphic as a single PNG file with transparency (alpha channel).
*   This must be done using the HTML Canvas API:
    *   Create a hidden canvas element with fixed dimensions of 1920 wide by 1080 high.
    *   Programmatically draw the graphic elements (shapes and text) onto this canvas using `ctx.fillStyle` and `ctx.font` based on the current state values (`text1`, `text2`, colors, `posX`, `posY`, `scale`).
    *   Use the Canvas `toDataURL('image/png')` method to generate the image data.
    *   Trigger a download using an anchor tag link.
