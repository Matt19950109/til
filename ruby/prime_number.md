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
