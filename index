# rules
import random
import art
print(art.logo)
# The deck is unlimited size
# There are no jockers
# The Jack/Queen?King all count as 10
# The Ace can count 11 or 1
# Use the following lists as the deck of cards


# The cards in the lists have the equal probability of being drawn
# cards do not remove from the deck as hey are drawn.
restart=True
while restart:
    game_over = False


    user_cards = []
    computer_cards = []
    computer_score=0
    user_score=0
    cards = [11, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10]

    # This function returns the random card into the cards list
    def deal_card():
        """"Return a random card from the deck"""
        cards = [11, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10]
        card = random.choice(cards)
        return card


    for _ in range(2):
        user_cards.append(deal_card())
        computer_cards.append((deal_card()))

    def calculation_score(cards):
        # Checking for a blackjack (a hand with only 2 cards: ace+10)and iretun 0 instead of the actual score .0 will represent a blackjack in our game
        if sum(cards) == 21 and len(cards) == 2:
            return 0
        if 11 in cards and sum(cards)>21 :
            cards.remove(11)
            cards.append(1)
        return sum(cards)
    while not game_over:
        user_score = calculation_score(user_cards)
        computer_score = calculation_score(computer_cards)
        print(f"your cards:{user_cards},current score={user_score}\ncomputer first cards:{computer_cards[0]} ")
        # if the computer or the user has a blackjack (0) or if the user's score is over 21,then the game end
        if computer_score == 0 or user_score == 0 or user_score > 21:
            game_over = True
        else:
            user_should_deal = input('Type "yes" to get another card otherwise type "no":')
            if user_should_deal == 'yes':
                user_cards.append((deal_card()))
            else:
                game_over = True

    # ONCE THE USER DONE ,IT'S TIME TO LET THE COMPUTER PLAY.THE COMPUTER SHOULD KEEP DRAWING CARDS AS LONG AS IT HAS SCORE LESS THAN 17
    while computer_score<17 and computer_score!=0:
        computer_cards.append(deal_card())
        computer_score=calculation_score(computer_cards)

    def compare(cs,us):
        if cs==us:
            return("its is a draw.")
        elif cs==0 :
            return("You loose the game")
        elif us>21:
            return ("You went the over, opponent wins the game")
        elif us==0 :
            return("You wins the game")
        elif cs>21:
            return("Oponent went over, you win the game")
        elif us>cs:
            return("You win the game ")
        else:
            return("opponent wins, you loose")


    print(f"your cards:{user_cards},current score={user_score}\ncomputer cards:{computer_cards},computer score:{computer_score} ")
    print(compare(cs=computer_score,us=user_score))
    play_again=input("type 'yes' if you want to restart the game, else type 'no' :").lower()
    if play_again=='no':
        restart=False


