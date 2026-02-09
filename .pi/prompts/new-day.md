---
description: Add new day to README, commit previous day, and push
---

1. Read the README.md file and identify the most recent day entry
2. Determine the next day (following the date pattern in the file)
3. Check if a new week header is needed:
   - If the next day is Monday and the current week section doesn't cover it, add a new week header
   - Week headers should follow the format: "# Week of [Month Day] - [Month Day]" (e.g., "# Week of Feb 9 - 13")
   - Calculate the date range from Monday through Friday of that week
   - Insert the new week header at the top of the document (below the TODO section if present)
   - Add a separator line (---) below the new week header
4. Add a new day section with the next day's date
   - If this is a new week, add it under the new week header
   - If continuing the same week, add it at the top of the existing week section
5. Extract the previous day's content (everything under the most recent day heading until the next day/section)
6. Git add the README.md file
7. Create a commit with the previous day's content as the commit message (remove the day heading line from the message)
8. Git push to main
9. Confirm what was done

Use the exact date format shown in the README (e.g., "## Monday Jan 26 2026" or "## Friday Feb 6 2026")
