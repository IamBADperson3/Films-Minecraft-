command /shop:
    trigger:
        open virtual chest with size 3 named "&aمتجر الأدوات" to player
        format slot 11 of player with diamond sword named "&cسيف قوي - 100$" to close then run [make player execute "/buy sword"]
        format slot 13 of player with golden apple named "&6تفاحة ذهبية - 50$" to close then run [make player execute "/buy gapple"]

command /buy <text>:
    trigger:
        if arg 1 is "sword":
            if player's balance is at least 100:
                remove 100 from player's balance
                give diamond sword to player
                send "&aتم شراء السيف!" to player
            else:
                send "&cلا تملك ما يكفي من المال."
        if arg 1 is "gapple":
            if player's balance is at least 50:
                remove 50 from player's balance
                give golden apple to player
                send "&aتم شراء التفاحة!" to player
            else:
                send "&cلا تملك ما يكفي من المال."
