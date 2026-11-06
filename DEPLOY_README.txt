STEFFEN & NINI — READY BEFORE PHOTOS
Build date: 6 November 2026

WHAT IS INCLUDED
1. index.html
   - Public Wishes works with code PUBLIC
   - Personal invitation still uses ?i=GUESTCODE
   - Personal RSVP (Hadir/Tidak Hadir, attending pax, vegetarian pax, note)
   - WhatsApp/social preview metadata
   - Existing music, animations, lunar date, Android/iPhone fixes retained

2. admin-live.html — Admin V3.2
   - Guest 1, Guest 2, etc: title + name + meal
   - WhatsApp input in 08 format
   - RSVP metrics, filters, attending pax
   - Check-in status and action
   - Google Sheet sync includes RSVP/check-in
   - Clean Test Data tool with explicit DELETE TEST confirmation
   - Link to WO Check-in page

3. checkin.html
   - Mobile WO check-in view
   - Search by name, WhatsApp, code, or table
   - RSVP, reserved pax, vegetarian context
   - Check In / Undo Check-in / Actual pax

4. share-preview.png
   - Temporary no-photo WhatsApp/Open Graph preview
   - Replace this file later with the final photo-based preview using the SAME filename

5. firestore.rules
   - Public RSVP validation against reserved seats
   - Admin and staff permissions
   - Public Wishes/Open tracking retained
   - Check-in permissions

6. Code.gs — Google Sheet Sync V7
   - Invitations includes RSVP and check-in fields
   - Creates RSVP and Check-in tabs automatically
   - Guest Members, Tables, Wishes Backup retained

7. sync-callback.html
   - Existing Google Sheet sync confirmation callback

DEPLOY ORDER

A. FIREBASE RULES
Firebase Console > Firestore Database > Rules
Replace all rules with firestore.rules, then Publish.

B. GOOGLE APPS SCRIPT
Open the existing sync project.
Replace Code.gs with Code.gs from this pack.
Save.
Deploy > Manage deployments > Edit > New version.
Execute as: Me.
Who has access: Anyone.
Deploy.
The existing Web App URL can remain unchanged.

C. GITHUB ROOT
Replace:
- index.html
- admin-live.html
- sync-callback.html

Upload:
- checkin.html
- share-preview.png

Keep unchanged:
- firebase-config.js
- music.mp3

D. FINAL TEST
1. General URL: Wishes sends successfully.
2. Personal URL: RSVP loads and saves.
3. Admin: RSVP metrics update.
4. checkin.html: login, check in one test guest, undo check-in.
5. Admin: Sync to Google Sheet.
6. Google Sheet: verify Invitations, Guest Members, RSVP, Check-in, Tables, Wishes Backup.
7. Admin: Clean Test Data, then Sync again.

WO SEPARATE LOGIN (OPTIONAL, NO CODE CHANGE)
1. Firebase Authentication > Add user for WO.
2. Copy WO UID.
3. Firestore Database > Data > create collection staffUsers.
4. Document ID = WO UID.
5. Add fields: role = "WO", active = true.
The published rules permit staffUsers to read guest operations and use check-in.

WHEN PHOTOS ARRIVE
Only these assets need to be added:
- opening/cover photo
- hero photo
- editorial gallery photos
- closing photo
- replace share-preview.png with a photo-based 1200x630 image

No database or workflow rebuild is required.
