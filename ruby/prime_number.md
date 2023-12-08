## 素数の記述コード
    primes = [2,3,5,7,11,13,17,19]
    count = 0
    primes.each do |prime|
      if 23 % 2 == 0
        count += 1
      end
    end
    
    if count == 0
      puts "23 is prime"
    else
      puts "23 is not prime"
    end

## 答えは5348
        n = 122
        count = 0
        
        while count < 40
          n = (n * 1.1).floor
          count += 1
        end
        
        p n
