# うるう年の記述方法

if month == 2
  if year % 4 == 0
    if year % 100 == 0 && year % 400 != 0
      days = 28
    else
      days = 29
    end
  days = 29
  end
  days = 28
end
