# Proposal Feedback Tool

Proposal Feedback Tool is a command-line application designed for freelancers who want a quick, constructive review of a client proposal before submitting it. It sends your proposal to Google's Gemini AI and produces:

- One specific strength
- One important, actionable weakness
- A clearer, more compelling rewrite of the opening sentence

The rewrite is designed to remain truthful to the proposal and avoid inventing experience, skills, or promises. Review all AI-generated suggestions carefully and confirm they accurately represent your work before using them.

## What This Solution Provides

This solution helps freelancers improve the quality of their proposals without needing a professional editor or copywriter. It delivers a fast, practical review of the proposal's messaging by:

- highlighting what is already working well
- identifying the biggest weakness or gap in the proposal
- suggesting a stronger opening sentence that remains accurate and credible

The application is built to make proposal writing easier, more confident, and more competitive while keeping the final wording under the user's control.

## Requirements

- Python 3.10 or later
- A Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey)
- An internet connection

## Installation

Open a terminal in this `proposal-feedback-tool` folder.

### Windows (PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install google-genai python-dotenv httpx
```

### macOS or Linux

```bash
python3 -m venv .venv
.venv/bin/python -m pip install google-genai python-dotenv httpx
```

Create a file named `.env` in this folder and add your API key:

```env
GEMINI_API_KEY=your_api_key_here
```

Replace `your_api_key_here` with your own key. Keep it private. The `.gitignore` file in this folder excludes `.env`, so the key is not added to Git.

Alternatively, set `GEMINI_API_KEY` in your terminal environment.

## Usage

### Paste a Proposal Interactively

Run the app without a proposal argument:

**Windows (PowerShell):**

```powershell
.\.venv\Scripts\python.exe .\main.py
```

**macOS or Linux:**

```bash
.venv/bin/python main.py
```

Paste your proposal. When finished, enter `END` on a line by itself and press Enter. The tool prints the strength, weakness, and rewritten opening sentence.

### Pass Proposal Text as an Argument

**Windows (PowerShell):**

```powershell
.\.venv\Scripts\python.exe .\main.py "I can build your booking website. I have experience with Python and React."
```

**macOS or Linux:**

```bash
.venv/bin/python main.py "I can build your booking website. I have experience with Python and React."
```

Use quotation marks around the proposal so it is passed as a single block of text. For longer proposals, the interactive method is more convenient.

To view command options, run `python main.py --help` (or use the virtual environment's Python executable as shown above).

## Example Interaction

```text
Paste your proposal below. Enter END on a line by itself when finished:
I can build your booking website. I have experience with Python and React.
END

Strength: You name relevant technologies and clearly identify the project.

Weakness: The proposal does not explain how your experience applies to this client's booking website.

Rewritten opening sentence: I can build your booking website using my experience with Python and React.
```

Gemini's wording may vary. The example is illustrative; the tool does not verify whether claims in a proposal are true.

## Privacy and Errors

The proposal text is sent to Google's Gemini API for review. Do not include confidential client details, passwords, or other sensitive information unless you have confirmed the applicable Google API data-use terms.

The tool reports empty proposals without making an API request. It also identifies rejected or unauthorized API keys and reports Gemini API errors, timeouts, connection problems, empty responses, and invalid or incomplete feedback in the terminal.

## Author

Branham Simiyu
