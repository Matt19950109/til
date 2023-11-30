# バブルソート　まとめ

- **バブルソート**…隣り合わせの値と交換を繰り返していく整列アルゴリズム  

    def bubble_sort(data)
      length = data.length 
      for i in 0..(length-1) 
        for j in 1.. (length-i-1) 
          if data[j-1] > data[j] 
            data[j-1],data[j] = data[j],data[j-1] 
          end
        end
      end
    end
