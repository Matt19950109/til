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

## 座標(X)
while i < 10
    j = 0
    horizontal_line = ''

    if i == y
      while j < 10
        horizontal_line += mark
        j += 1
      end
    else
      while j < 10
        if j == x
          horizontal_line += mark
        else
            horizontal_line += ' '
        end 
        j += 1
      end
    end
    puts horizontal_line
    i += 1
  end
  puts line
end
