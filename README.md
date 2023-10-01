on: 
push: 
branches: [ main ] 
pull_request: branches: [ main ] 
jobs: build: 
runs-on: ubuntu-latest 
steps: - 
uses: actions/checkout@v2 
name: "Gift card reader Test" run: echo "Testing" 
name: Build run: gcc -o giftcardreader giftcardreader.c 
name: Gift Card Reader Crashl 
run: ./giftcardreader 1 ./tests/crashl.gft 
name: Crash2 no file provided 
run: ./giftcardreader 1 
name: Gift Card Reader Hang 
run: ./giftcardreader 1 ./tests/hang.gft 
name: Fuzzer 1 
run: ./giftcardreader 1 ./fuzz/fuzzerl.gft 
name: Fuzzer 2 
run: ./giftcardreader 1 ./fuzz/fuzzer2.gft 
#name: Gift Card Reader Crash3 
#run: ./giftcardreader 1 ./tests/crash2.gft 
