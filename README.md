# Scripture App Administration Platform (SAAP)

**Project:** Scripture App Administration Platform

**Platform:** Web

**Tech used:** React, NodeJS, MySQL

**Wireframe:** [SAAP Figma](https://www.figma.com/file/wpL70RnSDaEgL4etThGDXl/SAAP?type=design&node-id=6%3A173&mode=design&t=Z6JwZ517IzMyUrAt-1)

This project aims to have a platform where Scripture texts are managed and made accessible to any platform via API.

## Module 1: Administrator Account User
- The platform can be authenticated by Administrator Account User.
- Administrator Account Users can be created, updated, and deleted except for the root Administrator Account.
- Only the root Administrator Account reset their passwords.

## Module 2: Bible
This is the core feature of this platform.
- The platform will read and extract files from a zip file uploaded by Administrator.
    - The extracted files include files formated with [USFM Standard](https://ubsicap.github.io/usfm/) (.usfm or .sfm), metainfo (`BookNames.xml`). Refer to this [sample-usfm folder](./assets/input-sample-usfm/).
    - After uploaded, the platform will check invalid markers and missing verses. See these files: valid-markers, complete-verses
- The platform will convert USFM format to: 

    1. [CSV](./assets/output-sample-csv.txt) 
    2. [JSON](./assets/output-sample-json.txt) 
    3. [XHTML](./assets/output-sample-xhtml/)
    4. [USX](./assets/output-sample-usx/)

        Note: If conversion to the last two formats (XHTML, USX) are extremely challenging, it can be excluded.
    - The converted files can be accessible via API with tokens.

## Module 3: Subscribed User
- Subscribed User and other info can be created, deleted, and updated by Administrator Account User
- Subscribed User can be registered via API. 







