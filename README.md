CHATAPP – PART 2 (Messaging System)

What Part 2 adds:
- After login, user sees a menu:
  1. Send Messages
  2. Show recently sent messages (Coming Soon)
  3. Quit
- User chooses how many messages to send.
- For each message:
  * Recipient phone number validated (SA format +27 and 9 digits).
  * Message text checked (max 250 chars; shows excess if longer).
  * System auto‑generates:
    - Message ID (10 random digits)
    - Message number (1,2,3...)
    - Message hash (first2digits:number:FIRSTWORDLASTWORD in uppercase, punctuation removed)
  * User can: Send, Disregard, or Store (Store saves to JSON file).
  * After choice, message details (ID, hash, recipient, text) are displayed.
- After all messages, total messages sent is shown.
- Menu repeats until user chooses Quit.

Unit tests (MessageTest.java) – 5 tests:
  - Short message (≤250 chars) passes.
  - Long message (260 chars) shows excess = 10.
  - Valid SA phone number accepted.
  - Invalid phone number rejected.
  - Message hash matches POE case "00:0:HITONIGHT" and format rules (loop test).

How to run:
1. Compile: javac chatapp/*.java
2. Run: java chatapp.ChatApp
3. Follow registration/login, then use menu option 1.

Run tests:
java -cp .:junit-4.13.2.jar:hamcrest-core-1.3.jar org.junit.runner.JUnitCore chatapp.MessageTest

JSON storage: Stored messages are appended to data.json (or chatdata.json) in the project folder.

GitHub requirements:
- Minimum 6 commits for Part 2.
- GitHub Actions runs all tests automatically on push.

All POE Part 2 requirements are met.
