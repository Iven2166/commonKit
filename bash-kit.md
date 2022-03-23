# bash common kit

- We have a file named 'test.csv'.
```bash
"id","product_uid","product_title","search_term","relevance"
2,100001,"Simpson Strong-Tie 12-Gauge Angle","angle bracket",3
3,100001,"Simpson Strong-Tie 12-Gauge Angle","l bracket",2.5
9,100002,"BEHR Premium Textured DeckOver 1-gal. #SC-141 Tugboat Wood and Concrete Coating","deck over",3
16,100005,"Delta Vero 1-Handle Shower Only Faucet Trim Kit in Chrome (Valve Not Included)","rain shower head",2.33
17,100005,"Delta Vero 1-Handle Shower Only Faucet Trim Kit in Chrome (Valve Not Included)","shower only faucet",2.67
18,100006,"Whirlpool 1.9 cu. ft. Over the Range Convection Microwave in Stainless Steel with Sensor Cooking","convection otr",3
20,100006,"Whirlpool 1.9 cu. ft. Over the Range Convection Microwave in Stainless Steel with Sensor Cooking","microwave over stove",2.67
21,100006,"Whirlpool 1.9 cu. ft. Over the Range Convection Microwave in Stainless Steel with Sensor Cooking","microwaves",3
23,100007,"Lithonia Lighting Quantum 2-Light Black LED Emergency Fixture Unit","emergency light",2.67
```
- edit text file
  - [vim](https://www.runoob.com/linux/linux-vim.html)
- count lines (rows)
    - wc -l test.csv
- count columns 
    - awk -F',' '{print NF;exit}' test.csv
    - head -10 test.csv | awk -F',' '{print NF}'
- return some lines
    - head -10 test.csv
- create a little file of copy
    - head -20 test.csv >> tmp.csv
  

- wc -w name.file 

wc --help
```bash
The options below may be used to select which counts are printed, always in
the following order: newline, word, character, byte, maximum line length.
  -c, --bytes            print the byte counts
  -m, --chars            print the character counts
  -l, --lines            print the newline counts
      --files0-from=F    read input from the files specified by
                           NUL-terminated names in file F;
                           If F is - then read names from standard input
  -L, --max-line-length  print the maximum display width
  -w, --words            print the word counts
      --help            显示此帮助信息并退出
      --version         显示版本信息并退出
```

