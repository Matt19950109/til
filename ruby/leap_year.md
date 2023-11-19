# うるう年の記述方法

if month == 2<br>
  if year % 4 == 0<br>
    if year % 100 == 0 && year % 400 != 0<br>
      days = 28<br>
    else<br>
      days = 29<br>
    end<br>
  days = 29<br>
  end<br>
  days = 28<br>
end<br>
