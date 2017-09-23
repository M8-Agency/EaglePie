# Eagle-Pie (Eagle-Eye's) Back-End

## How it (should) work

#### Find person

- If the user does a text search (no picture), we hit the Google Person Finder API directly (no need to hit this server)

- If the user does a picture search, we hit our server and look into our pictures database.

#### Safe person picture upload

- When the user submits a text collaboration, we hit the Google Person Finder API directly (no need to hit this server)

- When the user submits a photo collaboration (single picture or batch of pictures) we use Amazon's Rekognition `compare_faces()` method to detect equality. If the face is recognized within an acceptable threshold we will save the match flag on our nosql list of pictures and we will email the user about the possible match. If we matched correctly, the user will be happy. If we matched incorrectly we should provide a mechanism for rejection.


## Contributors

- Mohamed Dhia Soussi @modsoussi
- Antonio Rodriguez Martinez @antoniwan
