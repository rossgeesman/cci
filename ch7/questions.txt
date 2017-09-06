## 7.1
Major objects

Deck
Card
Suit
Number
```
class Deck
  attr_accessor :cards
  # Highly dependent on what we mean by 'generic' but if a standard 52 card deck of playing cards then I would go with this.
  
  def initialize
    @cards = []  
  end
end

class Card
  def initialize
    @suit = nil
    @number = nil
  end
end

class Suit
  VALUES = {}
end
```