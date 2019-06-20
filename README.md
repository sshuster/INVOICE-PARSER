# INVOICE-PARSER
A project to extract information from invoices and purchase orders

## INSTRUCTIONS FOR CREATING TEMPLATES


RECOMMENDED PROCEDURE [ WHEN THE USER ONLY HAS THE INVOICE AND NOT THE
TEMPLATE]

-   FOR CREATING INVOICES GO INTO THE SUBDIRECTORY: 'CREATE TEMPLATE/'
-   IT IS REQUIRED YOU HAVE AN INVOICE IN THE FORMAT OF EITHER 'PDF' OR
    'JPG' TO PROCEED
-   PLACE/COPY THE INVOICE FILE INTO THE
    '\_\_\_\_\_\_SAMPLES\_\_\_\_\_\_(PDF or JPG)' FOLDER AND MAKE SURE
    YOU DO NOT HAVE ANY OTHER FILES IN THE FOLDER.

    \*\*\*\* DELETE UNNECESSARY FILES IN
    '\_\_\_\_\_\_SAMPLES\_\_\_\_\_\_(PDF or JPG)' FOLDER \*\*\*\*

-   RUN 'template maker.py' LOCATED IN THE SAME DIRECTORY
-   PROCEED ACCORDING TO THE PROMPTS IN THE SHELL(DISPLAY)

    \*\*\*\* '1' IS YES. '0' IS NO \*\*\*\*

-   IF ANY WRONG/UNRECOGNISED CHARACTER IS ENTERED BY MISTAKE, CLOSE AND
    RUN THE PROGRAM AGAIN.
-   THE PROGRAM WILL PROCESS THE GIVEN INVOICE AND PLACE IT IN THE
    '\_\_\_\_\_EDIT THIS\_\_\_\_\_\_(JPG)' FOLDER.
-   OPEN THE IMAGE(JPG) IN THE '\_\_\_\_\_EDIT THIS\_\_\_\_\_\_(JPG)'
    FOLDER USING PAINT. (OPEN WITH -\> PAINT)
-   LOCATE WHERE IMPORTANT INFORMATION IS LOCATED (INVOICE NUMBER,
    DATE,ETC.)
-   AREAS WITH REQUIRED INFO MUST BE IN WHITE. EVERYTHING ELSE MUST BE
    IN BLACK
-   IMPORTANT TO MAKE THE WHITE RECTANGLES SLIGHTLY BIGGER THAN THE SIZE
    REQUIRED TO SUPPORT IMPROPERLY SCANNED INVOICES
-   ALSO IMPORTANT TO INCLUDE TOTAL AMOUNT IN BOTH NUMBERS AND IN
    WORDS(IF AVAILABLE)
-   ONCE FINISHED EDITING IN PAINT: SAVE AS -\> JPEG IMAGE -\> [default
    name]

    \*\*\*\* SAVE AS EDITED IMAGE IN '\_\_\_\_EDITED\_\_\_\_(JPG)'
    FOLDER \*\*\*\*

-   THE PROGRAM PROMPTS YOU TO ENTER '1' WHEN COMPLETED. PROCEED WHEN
    DONE
-   ENTER THE VENDOR NAME IN LOWER CASE AS PRESENT IN THE INVOICE WHEN
    PROMPTED IN THE PROGRAM
-   AFTER THE PROGRAM FINISHES PROCESSING IT WILL DISPLAY THE TEXT IT
    HAS RECOVERED
-   OPEN THE 'Templates.xlsx. LOCATED IN THE SAME DIRECTORY WITHOUT
    CLOSING THE PROGRAM (OPENING THE EXCEL SHEET PRIOR TO RUNNING THE
    PROGRAM IS ALSO PERMITTED) (SPLIT SCREEN RECOMMENED)
-   IN THE EXCEL SHEET:
    -   CODE IS TO BE INCREMENTED BY '1'
    -   VENDOR NAME IS TO BE ENTERED AS PRESENT IN THE INVOICE
    -   THE POSITION OF INVOICE NUMBER, INVOICE DATE, ETC. UNDER THEIR
        RESPECTIVE COLUMNS USING THE NUMBER SCHEME BELOW
    -   QUESTIONS ABOUT SPACES SHOULD BE ANSWERED IN '1' FOR YES, '0'
        FOR NO, '[character]' IF THERE IS A CHARACTER PRESENT BETWEEN
        THE DATA WITHOUT SPACES
    -   OTHER QUESTIONS NEED TO BE ANSWERED IN YES [1] OR NO [0]
    -   IF AMOUNT IN NUMBERS IS CLEARLY PRESENT IN THE OUTPUT USE IT'S
        POSITION ELSE USE THE POSITION OF THE AMOUNT IN WORDS AND ENTER
        '1' WHEN ASKED IF THE AMOUNT IS IN WORDS (IN THE EXCEL SHEET)

######################################################## 

NUMBER SCHEME: - THE POSITION OF AN ITEM FROM THE LEFT MUST BE IN
POSITIVE NUMBERS AND VICE VERSA - POSITIVE NUMBERING STARTS FROM '1'
[NOT '0']. NEGATIVE NUMBERING STARTS FROM '-1'. - IMPORTANT TO USE
POSITIVE NUMBERS WHEN INFORMATION IS ON THE LEFT SIDE OF THE ORIGINAL
INVOICE AND VICE VERSA

TYPES OF NOTATION: LET 'x' BE THE ROW NUMBER LET 'y' BE THE COLUMN
NUMBER

1.  IN THE CASE OF A SINGLE ITEM USE COMMAS. USE: x,y
2.  IN THE CASE OF MULTIPLE POSTIONS OF SAME INFO. USE: x1,y1;x2,y2
3.  IN THE CASE INFO SPANNING ACROSS MULTIPLE ITEMS. USE: x1,y1:x2,y2

FROM ABOVE, USE 2ND RULE WHEN ITEMS ARE ON DIFFERENT ROWS AND EITHER CAN
BE USED IF THE ARE CONTINUOUS (RECOMMENDED TO USE RULE 3). REFER
EXAMPLES BELOW FOR CLARIFICATION.

EXAMPLE:

The following output was received when creating a template for ISS
Machinery...

[ 1 ] ....... Sa OO secs

[ 2 ] ....... Cee 

[ 3 ] ....... 

[ 4 ] .......INVOICE DATE : April 20, 2019 

[ 5 ] ....... DELIVERY DATE : April 10, 2019 

[ 6 ] ....... INVOICE NO \>: — INV1904-02171 

[ 7 ] ....... SALES NO \> APSC1904-00059

[ 8 ] .......

[ 9 ] ....... GRAND TOTAL AMOUNT JPY188, 360, 00

ON THE LEFT IN SQUARE BRACKETS IS THE ROW NUMBER.

CONSIDER THE INVOICE NUMBER:

[ 6 ] ....... INVOICE NO \>: — INV1904-02171

SINCE IN THE ORIGINAL INVOICE IT IS PRESENT IN THE RIGHTMOST SIDE WE USE
NEGATIVE NUMBERS SEPARATE EACH CHARACTER/WORD BY SPACES AND NUMBER THEM
LIKE BELOW

                                              

[ 6 ] ....... INVOICE   NO  \>:    —      INV1904-02171



THEREFORE UNDER THE INVOICE NUMBER COLUMN IN THE EXCEL SHEET THE
FOLLOWING SHALL BE ENTERED: 6,-1

CONSIDER THE INVOICE DATE:

[ 4 ] ....... INVOICE DATE : April 20, 2019

USING NEGATIVE NUMBERING:

                

[ 4 ] ....... INVOICE DATE : April 20, 2019

NOTICE THAT THE DATE IS NOT ONE SINGLE ITEM. USING RULE NO.3 FROM ABOVE:

POSITION OF INVOICE DATE IS: 4,-3:4,-1

CONSIDER THE TOTAL AMOUNT AND CURRENCY: NOTICE THEY ARE ATTACHED TO EACH
OTHER. =\> ENTER '0' WHEN ASKED ABOUT SPACE BETWEEN CURRENCY AND TOTAL
AMOUNT

POSITIVE NUMBERING: [BECAUSE THERE ARE SPACES INBETWEEN THE AMOUNT]

                            

[ 9 ] ....... GRAND TOTAL AMOUNT JPY188, 360, 00

SINCE THERE ARE SPACES IN BETWEEN THE AMOUNT WE GIVE THE POSITION OF
ONLY THE FIRST NUMBER POSITION OF AMOUNT: 9,4 SINCE THEY ARE ATTACHED IT
IS NOT REQUIRED TO FILL THE POSITION OF CURRENCY

SINCE RS NUMBER IS NOT PRESENT, FILL '0' IN THE EXCEL SHEET WHERE IT IS
ASKED AND IT IS NOT REQUIRED TO FILL THE POSITIONS OF RS RELATED ITEMS

TYPICAL CASES:

1.CONSIDER THIS:

[ 3 ] .......INVOICE NO/DATE: 1222132/13.4.17

POSITION OF INVOICE NUMBER IS: 3,-1 SINCE THEY ARE ATTACHED IT IS NOT
REQUIRED TO FILL THE POSITION OF DATE WHERE IT IS ASKED TO ENTER IF
THERE IS A SPACE OR NOT (IN THE EXCEL SHEET), ENTER THE CHARACTER
BETWEEN THE ITEMS. =\> /

2.CONSIDER THIS:

[ 7 ] .......INVOICE DATE: 17 JULY,2018

THERE ARE ONLY TWO ITEMS WITH NUMBERING -2 -\>(17) AND -1 -\>(JULY,2018)

SO 7,-2;7,-1 CAN BE USED AND 7,-2:7,-1 CAN ALSO BE USED

3.CONSIDER THIS:

[ 12 ] .......TOTAL AMOUNT: 17,233

ASSUME THAT IN THE ORIGINAL INVOICE THIS INFORMATION IS PRESENT ON THE
LEFTSIDE

USING POSITIVE NUMBERING:

                

[ 12 ] .......TOTAL AMOUNT: 17,233

POSITION OF AMOUNT: 12,3

4.CONSIDER THIS:

[ 15 ] .......TOTAL AMOUNT: USD SEVENTY THOUSAND FIVE HUNDRED THRITY
FOUR ONLY

ASSUME IT IS ON RIGHTSIDE OF ORIGINAL INVOICE

IF AMOUNT IS IN WORDS USE POSITIVE NUMBERS ONLY AND GIVE THE POSITION OF
FIRST NUMBER ONLY

POSITION OF AMOUNT: 15,4 POSITION OF CURRENCY: 15,3

WHERE IT IS ASKED IF THE AMOUNT IS IN WORDS ENTER: '1'

######################################################## 

-   WHEN THE EXCEL SHEET IS FILLED REMEMBER TO SAVE THE WORKBOOK
-   PRESS ENTER IN THE PYTHON CONSOLE WINDOW TO CLOSE IT
-   END

ALTERNATIVE PROCEDURE: [WHEN THE USER HAS BOTH THE INVOICE AND THE
EDITED IMAGE READY]

-   PLACE THE ORIGINAL INVOICE IN THE
    '\_\_\_\_\_\_SAMPLES\_\_\_\_\_\_(PDF or JPG)' FOLDER
-   PLACE THE EDITED IMAGE IN THE '\_\_\_\_EDITED\_\_\_\_(JPG)' FOLDER
-   RUN 'template maker.py'.
-   WHEN PROMPTED IF YOU WANT TO USE THE FILE IN THE
    '\_\_\_\_EDITED\_\_\_\_(JPG)' FOLDER ENTER '1'
-   THEN FOLLOW THE SAME INSTRUCTIONS AS ABOVE

INSTRUCTIONS TO USE THIS PROGRAM IN ANOTHER PC ( WINDOWS VERSION \>= 7):
[NOT RECOMMENDED TO CREATE TEMPLATES IN MULTIPLE COMPUTERS BECAUSE
TEMPLATES ARE STORED LOCALLY AND UPDATES IN THE TEMPLATES WILL NOT BE
SEEN ON OTHER COMPUTERS]
- INSTALL PYTHON - USE pip TO INSTALL ALL
PACKAGES REQUIRED IN THE PROGRAM 
- Ghostscript - 'pip install
ghostscript' and https://www.ghostscript.com/download/gsdnld.html
- Imagemagick - https://imagemagick.org/script/download.php 
- Tesseract-OCR - https://github.com/UB-Mannheim/tesseract/wiki 
- INSTALL PYTHONMAGICK FROM WHEELS USING pip 
- INSTALL SCIPY 
- COPY THE COMPLETE '2.0' DIRECTORY IN NEW PC - THE PROGRAM IS READY TO BE USED

OTHER INSTRUCTIONS: 
- IF A VENDOR PERMANENTLY CHANGES THEIR TEMPLATE
FOLLOW THE SAME PROCEDURE AND REPLACE THE VALUES IN THE ROW ASSIGNED TO
THE SAME VENDOR IN THE EXCEL SHEET PREVIOUSLY

    **** DO NOT MAKE MULTIPLE ROWS FOR THE SAME VENDOR ****

-   IN CASE OF ERRORS IN THE PROGRAM, I.E. THE PROGRAM CLOSES WITHOUT AN
    OUTPUT, RIGHT CLICK ON template maker.py AND SELECT 'Edit with
    IDLE'. WHEN THE SCRIPT IS OPENED PRESS 'F5' TO RUN. THE ERROR WILL
    BE DISPLAYED AND THE PROGRAM CAN BE DEBUGGED ACCORDINGLY

   \*\*\*\* DO NOT MODIFY/DELETE/MOVE THE FILES AND FOLDERS IN ANY
    SUBDIRECTORY OF '2.0'\*\*\*\*

THIS PROJECT IS DISTRIBUTED UNDER THE MIT LICENSE FOR USE IN THE
SHIPPING CORPORATION OF INDIA ONLY

