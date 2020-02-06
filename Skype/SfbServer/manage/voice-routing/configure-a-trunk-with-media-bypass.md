---
title: Configurare un trunk con il bypass multimediale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Seguire questa procedura per configurare un trunk con il bypass multimediale abilitato. '
ms.openlocfilehash: 3628c0ea38c0692b313ee37ca7b836c159a5a2dd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817036"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurare un trunk con il bypass multimediale in Skype for Business Server

Seguire questa procedura per configurare un trunk con il bypass multimediale abilitato. Per configurare un trunk con il bypass multimediale disabilitato, vedere [configurare un trunk senza bypass multimediale in Skype for Business Server](configure-a-trunk-without-media-bypass.md). Il bypass multimediale è utile quando si vuole ridurre al minimo il numero di server di mediazione distribuiti. In genere, un pool di Mediation Server verrà distribuito in un sito centrale e controllerà i gateway nei siti di succursale. L'abilitazione del bypass multimediale consente alle chiamate PSTN (Public Switched Telephone Network) dei client in siti di succursale di scorrere direttamente attraverso i gateway in questi siti. Le route delle chiamate in uscita e i criteri VoIP aziendale di Skype for Business Server devono essere configurati correttamente in modo che le chiamate PSTN da client in un sito di succursale vengano indirizzate al gateway appropriato.

Ti consigliamo vivamente di abilitare il bypass multimediale. Tuttavia, prima di abilitare il bypass multimediale in un trunk SIP, verificare che il provider trunk SIP completo supporti il bypass multimediale ed è in grado di soddisfare i requisiti per l'abilitazione dello scenario. In particolare, il provider deve avere gli indirizzi IP dei server nella rete interna dell'organizzazione. Se il provider non supporta questo scenario, il bypass multimediale non avrà esito positivo. Per informazioni dettagliate, vedere [pianificare il bypass multimediale in Skype for business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> Il bypass multimediale non si interagisce con tutti i gateway PSTN (Public Switched Telephone Network), IP-PBX e Session Border Controller (SBC). Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con prodotti e versioni elencati nell' [infrastruttura di telefonia per la pagina Skype for Business Server](../../../SfbPartnerCertification/certification/infra-gateways.md) . 


Una configurazione trunk come descritto di seguito raggruppa un set di parametri applicati ai trunk assegnati a questa configurazione trunk. Una particolare configurazione trunk può essere portata a livello globale (per tutti i trunk che non dispongono di una configurazione di sito o di pool più specifica) o di un sito o di un pool. La configurazione del trunk a livello di pool viene usata per l'ambito di una configurazione trunk specifica in un singolo trunk.

**Per configurare un trunk con il bypass multimediale**

1. Aprire il pannello di controllo di Skype for busines server.
2. Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **configurazione trunk**.
3. Nella pagina **trunk Configuration** usare uno dei metodi seguenti per configurare un trunk:
    - Fare doppio clic su un trunk esistente, ad esempio il trunk **globale** , per visualizzare la finestra di dialogo **modifica configurazione trunk** .
    - Fare clic su **nuovo**e quindi selezionare un ambito per la nuova configurazione trunk:
        - **Trunk sito**: scegliere il sito per questa configurazione trunk da **Seleziona un sito**e quindi fare clic su **OK**. Tieni presente che se è già stata creata una configurazione trunk per un sito, il sito non viene visualizzato in **Seleziona un sito**. Questa configurazione trunk verrà applicata a tutti i trunk nel sito.
        - **Trunk pool**: scegliere il nome del trunk a cui si applica la configurazione del trunk. Questo trunk può essere il trunk radice o eventuali trunk aggiuntivi definiti in Generatore di topologia. In **Seleziona un servizio**fare clic su **OK**. Tieni presente che se è già stata creata una configurazione trunk per un trunk specifico, il trunk non viene visualizzato in **Seleziona un servizio**.
    
    > [!NOTE]
    > Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo. Il campo **nome** viene prepopolato con il nome del sito o del servizio associato alla configurazione del trunk e non può essere modificato. 

5. Specificare un valore nelle **finestre di dialogo iniziali massime supportate**. Questo è il numero massimo di risposte a forcella un gateway PSTN (IP-PBX) o ITSP session border controller (SBC) pubblico può ricevere un invito inviato al Mediation Server. Il valore predefinito è 20.

    > [!NOTE] 
    > Prima di modificare questo valore, consultare il provider di servizi o il produttore di attrezzature per informazioni dettagliate sulle funzionalità del sistema. 

6. Selezionare una delle opzioni seguenti per il **livello di supporto della crittografia** :
    - **Obbligatorio**: per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange), è necessario usare la crittografia SRTP (Real-Time Transport Protocol).
    - **Facoltativo**: la crittografia SRTP verrà usata se il provider di servizi o il produttore di attrezzature lo supporta.
    - **Non supportato**: la crittografia SRTP non è supportata dal fornitore di servizi o dal produttore di attrezzature e quindi non verrà usata.
7. Selezionare la casella di controllo **Abilita esclusione multimediale** se si vuole che il supporto venga ignorato dal server Mediation per l'elaborazione da parte del peer trunk.

    > [!IMPORTANT]
    > Per il corretto funzionamento del bypass multimediale, il gateway PSTN, IP-PBX o ITSP session border controller deve supportare alcune funzionalità. Per informazioni dettagliate, vedere [pianificare il bypass multimediale in Skype for business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Selezionare la casella di controllo **elaborazione multimediale centralizzata** se è presente un punto di interruzione del contenuto multimediale noto, ad esempio un gateway PSTN in cui la terminazione multimediale ha lo stesso IP della terminazione di segnalazione. Deselezionare questa casella di controllo se il trunk non ha un punto di interruzione multimediale noto.
9. Se il peer trunk supporta la ricezione delle richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Consenti invio di riferimento al gateway** . 

    > [!NOTE] 
    > Se si disattiva questa opzione mentre è selezionata l'opzione **Abilita bypass multimediale** , sono necessarie altre impostazioni. Se il peer trunk non supporta la ricezione delle richieste SIP REFER dal Mediation Server e il bypass multimediale è abilitato, è necessario eseguire anche il cmdlet **Set-CsTrunkConfiguration** per disabilitare RTCP per le chiamate attive e detenute, al fine di supportare le condizioni appropriate per il bypass multimediale. In alternativa, è possibile selezionare **Abilita riferimento tramite il controllo delle chiamate di terze parti** se si vuole che le chiamate trasferite vengano ignorate da elementi multimediali e il gateway non supporta le richieste di riferimento SIP. 

10. Opzionale Per abilitare il routing tra trunk, associa e configura i record di utilizzo PSTN alla configurazione del trunk. Gli usi PSTN associati alla configurazione del trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk non proveniente da un endpoint di Skype for Business Server. Per gestire i record di utilizzo PSTN associati a una configurazione trunk, usare uno dei metodi seguenti:
    - Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare i record che si desidera associare alla configurazione del trunk e quindi fare clic su **OK**.
    - Per rimuovere un record di utilizzo PSTN dalla configurazione del trunk, selezionare il record e fare clic su **Rimuovi**.
    - Per definire un nuovo record di utilizzo PSTN e associarlo alla configurazione del trunk, eseguire le operazioni seguenti:
        1. Fare clic su **nuovo**.
        2. Nel campo **nome** specificare un nome descrittivo per il record univoco.
            > [!NOTE] 
            > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo **nome** non può essere modificato. 
        3. Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:
            - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**. 
            - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
            - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**. 
            - Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**. 
        4. Fare clic su **OK**.
    - Per modificare un record di utilizzo PSTN già associato alla configurazione del trunk, eseguire le operazioni seguenti:
        1. Selezionare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.
        2. Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:
            - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**. 
            - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
            - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**. 
            - Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**. 
        3. Fare clic su **OK**.

    > [!Important]
    > È importante associare i record di utilizzo PSTN in base al peer di Mediation Server associato al trunk configurato. Se il peer di Mediation Server è un gateway PSTN o un SBC (Session Border Controller), è consigliabile che la configurazione trunk non sia associata a un record di utilizzo PSTN che si indirizza a una destinazione PSTN o a qualsiasi altro sistema a valle connesso tramite Skype for Business Server. 

11. Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce in su o in giù.

    > [!Important]
    > L'ordine in cui sono elencati i record di utilizzo PSTN nella configurazione trunk è significativo. Skype for Business Server attraversa l'elenco dall'alto verso il basso. 

12. **Abilitare il latching RTP** deve essere selezionato per consentire l'esclusione di elementi multimediali per i client dietro un NAT (Network Address Translation) o un firewall e un SBC che supporta il blocco.
13. **Abilitare la cronologia delle chiamate in avanti** deve essere selezionata per consentire l'invio di informazioni sulla cronologia delle chiamate al peer del gateway del Mediation Server.
14. **Abilita inoltro p-asserzione-i dati di identità** devono essere selezionati per consentire l'inoltro delle informazioni sull'origine delle chiamate p-Asserted-Identity (PAI) tra il lato Mediation Server e il lato gateway (e viceversa), quando presenti.
15. **Abilitare il timer di failover del routing in uscita** deve essere selezionato per consentire il failover veloce. Il gateway associato a questo trunk può dare notifica entro 10 secondi che sta elaborando una chiamata in uscita. La reinstradazione a un altro trunk si verificherà se la notifica non viene ricevuta dal Mediation Server. Nelle reti in cui la latenza può ritardare il tempo di risposta o il gateway richiede più di 10 secondi per rispondere, il failover veloce deve essere disabilitato.
16. Opzionale Associa e configura le **regole di traduzione del numero chiamante** per il trunk. Queste regole di traduzione si applicano al numero chiamante per le chiamate in uscita.
    - Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.
    - Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione in Skype for Business Server](defining-translation-rules.md).
    - Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Skype for Business Server](defining-translation-rules.md).
    - Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Skype for Business Server](defining-translation-rules.md).
    - Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.
    > [!Warning]
    > Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto. 

17. Opzionale Associare e configurare **le regole di traduzione dei numeri** per il trunk. Le regole di traduzione si applicano al numero chiamato in una chiamata in uscita.
    - Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.
    - Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione in Skype for Business Server](defining-translation-rules.md).
    - Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Skype for Business Server](defining-translation-rules.md).
    - Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Skype for Business Server](defining-translation-rules.md).
    - Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

    > [!Warning] 
    > Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto. 

18. Verificare che le regole di traduzione del trunk siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia in su o in giù.

    >[!Important] 
    > Skype for Business Server attraversa l'elenco delle regole di traduzione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato. Se si configura un trunk in modo che un numero composto possa corrispondere a più regole di traduzione, assicurarsi che le regole più restrittive siano ordinate al di sopra delle regole meno restrittive. Se ad esempio è stata inclusa una regola di traduzione che corrisponde a qualsiasi numero di 11 cifre e a una regola di traduzione che corrisponde a solo numeri a 11 cifre che iniziano con + 1425, assicurarsi che la regola che corrisponde a qualsiasi numero di 11 cifre sia ordinata *sotto* la regola più restrittiva. 

19. Al termine della configurazione del trunk, fare clic su **OK**.
20. Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**. 

    > [!Note]
    > Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso nella configurazione del routing vocale](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). (SERVE UN NUOVO COLLEGAMENTO?)

Dopo aver configurato il trunk, continuare a configurare il bypass multimediale scegliendo tra le opzioni di bypass multimediale globale, come descritto in [distribuire il bypass multimediale in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).

