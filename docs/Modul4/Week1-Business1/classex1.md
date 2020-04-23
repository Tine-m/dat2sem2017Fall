# Klasse øvelse

### Lav et aktivitetsdiagram over følgende work flow:

I denne virksomhed kan en **opgavestiller** stille opgaver, som han ønsker andre skal løse.   

Når en sådan opgave er stillet tjekker et **IT-system** automatisk om opgavebeskrivelsen indeholder de relevante informationer.   

Såfremt dette ikke er tilfældet, vender opgaven tilbage til opgavestiller, som skal reformulere opgaven.   

Hvis opgaven indeholder informationer tjekker den **kvalitetsansvarlige** om opgaven er beskrevet på en måde, som er forståelig. Hvis dette ikke er tilfældet vender opgaver tilbage til opgavestiller.   

Såfremt beskrivelsen er god nok tilføjer den kvalitetsansvarlige en test til opgaven og sender  opgaven og testen til en **udvikler**, som herefter estimerer hvor lang tid det vil tage at løse opgaven.   

Estimatet sendes til opgavestiller, som enten godkender estimatet og meddeler udvikleren, at han kan gå i  gang med at kode opgaven eller afviser estimatet og trækker opgaven tilbage.   

Når udvikleren har løst opgaven, flytter IT systemet opgaven over til en **tester**, som tester om opgaven er godt nok løst.   

Hvis dette ikke er tilfældet går opgaven tilbage til udvikleren med en rapport om problemer i test.   

Såfremt opgaven klarer testen vender opgaven incl. løsningen af opgaven tilbage til opgavestiller.