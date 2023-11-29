# while文の数字の変遷についてまとめています

## 例１
x = 0
y = 0
z = 0

while x < 4
  if x % 2 == 0
    y += x - 1
  end
  x += 1
end

puts x
puts y

- **x → 4 y → 0が出力される**
