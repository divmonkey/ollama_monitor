# Ollama Monitor Setup Instructions

## Fixing CORS Blocking

If you see a **CORS Blocking Detected** warning when opening the monitoring panel, follow these steps:

1. **Close Ollama completely**
   - Check the system tray and close any terminal running `ollama serve`.

2. **Run Ollama with CORS enabled**
   - Open PowerShell and run:
     ```powershell
     $env:OLLAMA_ORIGINS="*"; ollama serve
     ```

3. **Serve the HTML file through a local server**
   - Do **not** double-click the file.
   - Instead, run:
     ```powershell
     npx serve .
     ```
   - Then open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Why this happens

Browsers block cross-origin requests from `file://` pages for security.  
- Setting `OLLAMA_ORIGINS=*` tells Ollama to accept requests from any origin.  
- Using a local server avoids the `file://` restriction entirely.

---

## Screenshots

### Main Panel
![Main Panel](https://github.com/divmonkey/ollama_monitor/blob/main/main_panel.png)

### Debug Panel
![Debug Panel](https://github.com/divmonkey/ollama_monitor/blob/main/debug.png)
