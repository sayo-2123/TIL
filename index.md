# 20230507
  -paizaCランク学習
    -配列
## ボール回し
  
   # 人数 N を入力
  n = gets.to_i

  # 各人が持つボールの個数を配列で保持
  balls = []
  n.times do
    balls << gets.to_i
  end

  # パス回しの情報数 M を入力
  m = gets.to_i

  # パス回しの情報をもとにボールをパスする
  m.times do
    a, b, x = gets.split.map(&:to_i)
    a -= 1  # 配列のインデックスは 0 から始まるため、1 を引く
    b -= 1
    pass_num = [balls[a], x].min  # パスするボールの個数
    balls[a] -= pass_num
    balls[b] += pass_num
  end

  # 各人の最終的なボールの個数を出力
  balls.each do |ball|
    puts ball
  end

##ハイローゲーム
  # 親カードの情報を入力する
  parent = gets.chomp.split.map(&:to_i)
  
  # 子カードの情報を入力する
  n = gets.chomp.to_i
  cards = []
  n.times do
    cards << gets.chomp.split.map(&:to_i)
  end
  
  # 子カードと親カードを比較する
  cards.each do |card|
    if card[0] > parent[0] || (card[0] == parent[0] && card[1] < parent[1])
      puts "High"
    else
      puts "Low"
    end
  end
