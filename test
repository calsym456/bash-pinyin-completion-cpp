mkdir -p "测试"
correct=0
if [[ $(./bash-pinyin-completion ce -f) == "测试" ]]; then
  echo "Test 1 PASSED"
  ((correct += 1))
else
  echo "Test 1 NOT PASSED"
fi

if [[ $(./bash-pinyin-completion ./ce -f) == "./测试" ]]; then
  echo "Test 2 PASSED"
  ((correct += 1))
else
  echo "Test 2 NOT PASSED"
fi

if [[ $(wc -l <<<"$(./bash-pinyin-completion /usr/lib -f)" | xargs) == 2 ]]; then
  echo "Test 3 PASSED"
  ((correct += 1))
else
  echo "Test 3 NOT PASSED"
fi

if [[ $(wc -l <<<"$(./bash-pinyin-completion /usr/lib/ -f)" | xargs) -gt 3 ]]; then
  echo "Test 4 PASSED"
  ((correct += 1))
else
  echo "Test 4 NOT PASSED"
fi

rm -r "测试"
if [[ correct < 4 ]]; then
  exit 1
fi

exit 0
