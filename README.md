# Camp Notion Integration (FORGE)

This project adds a small Notion API integration for the "Preparation" flow.

Quick start

1. Install dependencies:

   npm install

2. Create an integration in Notion and share the target page with the integration (see https://developers.notion.com/docs).

3. Copy `.env.template` to `.env` and set `NOTION_TOKEN` to your integration's secret.

4. Start the server (it will serve `index.html` at the same origin):

   npm start

5. Open http://localhost:3000 in your browser and click the "Open Preparation (Notion)" button.

Notes

- The server exposes `/api/notion?pageId=PAGE_ID` which fetches the Notion page's blocks and returns JSON. The client-side code in `index.html` renders basic block types (paragraphs, headings, lists, images).
- For production, do not expose your Notion token in client-side code. Keep it in server environment variables.
- This implementation fetches only the first page of blocks (page_size=100). For long pages you'd want to page through children using the Notion API's pagination.
