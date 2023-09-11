# Dummy Paratext Project

> ⚠️ Files here are purposedly distored to protect abuse of copyrighted content.

Paratext Software မှ Backup ထုတ်လိုက်သော files များထဲမှ data manipulation အတွက် မှီငြမ်းရန် လိုအပ်သော files များ ဖြစ်ပါသည်။

File Type | Description
------------ | ------------
.SFM (.USFM) | LeTex ကိုတုပ၍တည်ဆောက်ထားသော Unified Standard Format Markers (USFM) format ဖြစ်သည်။
BookNames.xml | ထို xml file တွင် book names အတိုကောက် `abbr`၊ book names နာမည်အရှည် `long` ၊ book names နာမည်အတို `short` နှင့် book code `code` များပါဝင်သည်။

# .USFM (.SFM)

File extension ကို `.USFM` (သို့) `.SFM` ဖြင့် အဆုံးသတ်သည်။ 

File name ၏ ပထမဦးဆုံး ကိန်း (၂)လုံးသည် `01` မှ `66` အထိရှိသည်။

Number Series | Book Code | Testament Type
------------ | ------------- | -------------
01 | GEN | OLD TESTAMENT
02 | EXO | OLD TESTAMENT
03 | LEV | OLD TESTAMENT
04 | NUM | OLD TESTAMENT
05 | DEU | OLD TESTAMENT
06 | JOS | OLD TESTAMENT
07 | JDG | OLD TESTAMENT
08 | RUT | OLD TESTAMENT
09 | 1SA | OLD TESTAMENT
10 | 2SA | OLD TESTAMENT
11 | 1KI | OLD TESTAMENT
12 | 2KI | OLD TESTAMENT
13 | 1CH | OLD TESTAMENT
14 | 2CH | OLD TESTAMENT
15 | EZR | OLD TESTAMENT
16 | NEH | OLD TESTAMENT
17 | EST | OLD TESTAMENT
18 | JOB | OLD TESTAMENT
19 | PSA | OLD TESTAMENT
20 | PRO | OLD TESTAMENT
21 | ECC | OLD TESTAMENT
22 | SNG | OLD TESTAMENT
23 | ISA | OLD TESTAMENT
24 | JER | OLD TESTAMENT
25 | LAM | OLD TESTAMENT
26 | EZK | OLD TESTAMENT
27 | DAN | OLD TESTAMENT
28 | HOS | OLD TESTAMENT
29 | JOL | OLD TESTAMENT
30 | AMO | OLD TESTAMENT
31 | OBA | OLD TESTAMENT
32 | JON | OLD TESTAMENT
33 | MIC | OLD TESTAMENT
34 | NAM | OLD TESTAMENT
35 | HAB | OLD TESTAMENT
36 | ZEP | OLD TESTAMENT
37 | HAG | OLD TESTAMENT
38 | ZEC | OLD TESTAMENT
39 | MAL | OLD TESTAMENT
40 | MAT | NEW TESTAMENT
41 | MRK | NEW TESTAMENT
42 | LUK | NEW TESTAMENT
43 | JHN | NEW TESTAMENT
44 | ACT | NEW TESTAMENT
45 | ROM | NEW TESTAMENT
46 | 1CO | NEW TESTAMENT
47 | 2CO | NEW TESTAMENT
48 | GAL | NEW TESTAMENT
49 | EPH | NEW TESTAMENT
50 | PHP | NEW TESTAMENT
51 | COL | NEW TESTAMENT
52 | 1TH | NEW TESTAMENT
53 | 2TH | NEW TESTAMENT
54 | 1TI | NEW TESTAMENT
55 | 2TI | NEW TESTAMENT
56 | TIT | NEW TESTAMENT
57 | PHM | NEW TESTAMENT
58 | HEB | NEW TESTAMENT
59 | JAS | NEW TESTAMENT
60 | 1PE | NEW TESTAMENT
61 | 2PE | NEW TESTAMENT
62 | 1JN | NEW TESTAMENT
63 | 2JN | NEW TESTAMENT
64 | 3JN | NEW TESTAMENT
65 | JUD | NEW TESTAMENT
66 | REV | NEW TESTAMENT


### Testament Type (3) မျိုး

Testament Type | Boolean
------------ | ------------- 
Old Testament + New Testament | 1
New Testament + PRO + PSA | 2
New Testament | 3


**Testament Type Checking အတွက် Sample Pseudocode**

```
filesCount = 27;

if filesCount == 66:
  setType(1)
elseif filesCount == 29:
  setType(2)
elseif filesCount == 27
 setType(3)
else:
 setError()
```

## BookNames.xml

BookNames.xml မှ Testament Table အတွက် လိုအပ်သော data မှာ ရယူရမည် ဖြစ်ပါသည်။
BookName.xml ၏ XML Scheme Table မှာ အောက်ပါအတိုင်းဖြစ်သည်။
**BookNames XML Table**
Attribute | Description
------------ | ------------ 
code | book code ကို ဆိုလိုသည်။ Testament Table အတွက် Traditional ဖြင့် sort ထားသော array ဖြစ်မြောက်ရန် code လိုအပ်သည်။
abbr | book names အတွက် အတိုကောက်ဖြစ်ပါသည်။ Testament Table အတွက် မလိုအပ်ပါ။
short | book names အတွက် နာမည် အတိုဖြစ်ပါသည်။ Testament Table အတွက် မလိုအပ်ပါ။
long | book names အတွက် နာမည် အပြည့်အစုံဖြစ်ပါသည်။ Testament Table အတွက် Book names array ထုတ်ရန် long ကို လိုအပ်သည်။

**Testament NoSQL Table Scheme**
Item | Type | Description  
------------ | ------------ | ------------ 
ot_array_traditional | Array String | Old Testament တွင် ပါဝင်သော book names များကို number series အလိုက် စီထားသော array ကို ဆိုလိုပါသည်။
ot_array_sorted | Array String | Old Testament တွင် ပါဝင်သော book names များကို alphabet အလိုက် စီထားသော array ကို ဆိုလိုပါသည်။
nt_array_traditional | Array String | New Testament တွင် ပါဝင်သော book names များကို number series အလိုက် စီထားသော array ကို ဆိုလိုပါသည်။
ot_array_sorted | Array String | New Testament တွင် ပါဝင်သော book names များကို alphabet အလိုက် စီထားသော array ကို ဆိုလိုပါသည်။
testament_type | Number | Testament type အမျိုးအစားကို ဆိုလိုသည်။ Value မှာ 1,2,3 ရှိသည်။ `1` သည် Old Testament နှင့် New Testment ပါဝင်သည်ဟု ဆိုလိုသည်။ `2` သည် PRO, PSA နှင့် New Testament ပါဝင်သည်ဟု ဆိုလိုသည်။ `3` သည် New Testament များသာ ပါဝင်သည်ဟု ဆိုလိုသည်။

