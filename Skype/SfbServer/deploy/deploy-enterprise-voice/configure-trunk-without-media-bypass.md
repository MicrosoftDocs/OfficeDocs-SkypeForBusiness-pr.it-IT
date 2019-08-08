---
title: Configurare un trunk senza bypass multimediale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Riepilogo: configurare un trunk senza bypass multimediale abilitato per Skype for Business Server.'
ms.openlocfilehash: c60217b6dc127616dfbaf9590c43adec25c20eff
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233879"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Configurare un trunk senza bypass multimediale in Skype for Business Server

**Riepilogo:** Configurare un trunk senza bypass multimediale abilitato per Skype for Business Server.

Se si vuole configurare un trunk con il bypass multimediale disabilitato, eseguire le operazioni seguenti. Se si vuole configurare un trunk con il bypass multimediale abilitato, vedere [configurare un trunk con il bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md).

Una configurazione trunk, come descritto di seguito, raggruppa un set di parametri applicati ai trunk assegnati alla configurazione del trunk. Una particolare configurazione trunk può essere portata a livello globale (per tutti i trunk che non dispongono di una configurazione di sito o di pool più specifica) o di un sito o di un pool. La configurazione del trunk a livello di pool viene usata per l'ambito di una configurazione trunk specifica in un singolo trunk.

### <a name="to-configure-a-trunk-without-media-bypass"></a>Per configurare un trunk senza bypass multimediale

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **configurazione trunk**.

3. Nella pagina **trunk Configuration** usare uno dei metodi seguenti per configurare un trunk:

   - Fare doppio clic su un trunk esistente, ad esempio il trunk **globale** , per visualizzare la finestra di dialogo **modifica configurazione trunk** .

   - Fare clic su **nuovo**e quindi selezionare un ambito per la nuova configurazione trunk:

   - **Trunk sito**: scegliere il sito per questa configurazione trunk in **selezionare un sito**e quindi fare clic su **OK**. Tieni presente che se è già stata creata una configurazione trunk per un sito, il sito non viene visualizzato in **Seleziona un sito**. Questa configurazione trunk verrà applicata a tutti i trunk nel sito.

   - **Trunk pool**: scegliere il nome del trunk a cui si applica la configurazione del trunk in **selezionare un servizio** e fare clic su **OK**. Questo trunk può essere il trunk radice o altri trunk definiti in Generatore di topologia. Tieni presente che se è già stata creata una configurazione trunk per un trunk specifico, il trunk non viene visualizzato in **Seleziona un servizio**.

     > [!NOTE]
     > Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo. > il campo **nome** viene prepopolato con il nome del sito o del servizio associato alla configurazione del trunk e non può essere modificato.

4. Selezionare una delle opzioni seguenti per il **livello di supporto della crittografia** :

   - **Obbligatorio**: la crittografia SRTP (Secure Realtime Transport Protocol) deve essere usata per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange).

   - **Facoltativo**: la crittografia SRTP verrà usata se il provider di servizi o il produttore di attrezzature lo supporta.

   - **Non supportato**: la crittografia SRTP non è supportata dal fornitore di servizi o dal produttore di attrezzature e quindi non verrà usata.

5. Assicurarsi che la casella di controllo **Abilita esclusione multimediale** sia deselezionata.

6. Selezionare la casella di controllo **elaborazione multimediale centralizzata** se è presente un punto di interruzione del contenuto multimediale noto, ad esempio un gateway PSTN (Public Switched Telephone Network) in cui la terminazione multimediale ha lo stesso IP della terminazione di segnalazione. Deselezionare questa casella di controllo se il trunk non ha un punto di interruzione multimediale noto.

7. Se il peer trunk supporta la ricezione delle richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Consenti invio di riferimento al gateway** .

8. Opzionale Per abilitare il routing tra trunk, associa e configura i record di utilizzo PSTN alla configurazione del trunk. Gli usi PSTN associati alla configurazione del trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk non proveniente da un endpoint di Skype for Business Server. Per gestire i record di utilizzo PSTN associati a una configurazione trunk, usare uno dei metodi seguenti:

   - Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare i record che si desidera associare alla configurazione del trunk e quindi fare clic su **OK**.

   - Per rimuovere un record di utilizzo PSTN dalla configurazione del trunk, selezionare il record e fare clic su **Rimuovi**.

   - Per definire un nuovo record di utilizzo PSTN e associarlo alla configurazione del trunk, eseguire le operazioni seguenti:

     un. Fare clic su **nuovo**.

     b. Nel campo **nome** specificare un nome descrittivo per il record univoco.

     > [!NOTE]
     > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo **nome** non può essere modificato.

     c. Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:

     - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**.

     - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.

     - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

     - Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.

     3D. Fare clic su **OK**.

   - Per modificare un record di utilizzo PSTN già associato alla configurazione del trunk, eseguire le operazioni seguenti:

     un. Selezionare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.

     b. Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:

     - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**.

     - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.

     - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare o modificare una route vocale in Skype for business](create-or-modify-a-voice-route.md).

     - Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.

     c. Fare clic su **OK**.

     > [!IMPORTANT]
     > È importante associare i record di utilizzo PSTN in base al peer di Mediation Server associato al trunk configurato. Se il peer di Mediation Server è un gateway PSTN o un SBC (Session Border Controller), è consigliabile che la configurazione trunk non sia associata a un record di utilizzo PSTN che si indirizza a una destinazione PSTN o a qualsiasi altro sistema a valle connesso tramite Skype for Business Server.

9. Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce in su o in giù.

    > [!IMPORTANT]
    > L'ordine in cui sono elencati i record di utilizzo PSTN nella configurazione trunk è significativo. Skype for Business Server attraversa l'elenco dall'alto verso il basso.

10. **Abilitare il latching RTP** deve essere selezionato per consentire l'esclusione di elementi multimediali per i client dietro un NAT o un firewall e un SBC che supporta il blocco.

11. **Abilitare la cronologia delle chiamate in avanti** deve essere selezionata per consentire l'invio di informazioni sulla cronologia delle chiamate al peer del gateway del Mediation Server.

12. **Abilita inoltro P-asserzione-i dati di identità** devono essere selezionati per consentire l'inoltro delle informazioni sull'originatore delle chiamate di Pai tra il lato Mediation Server e il lato gateway (e viceversa), quando presenti.

13. **Abilitare il timer di failover del routing in uscita** deve essere selezionato per consentire il failover veloce. Il gateway associato a questo trunk può dare notifica entro 10 secondi che sta elaborando una chiamata in uscita. La reinstradazione a un altro trunk si verificherà se la notifica non viene ricevuta dal Mediation Server. Nelle reti in cui la latenza può ritardare il tempo di risposta o il gateway richiede più di 10 secondi per rispondere, il failover veloce deve essere disabilitato.

14. Opzionale Associa e configura le **regole di traduzione del numero chiamante** per il trunk. Queste regole di traduzione si applicano al numero chiamante per le chiamate in uscita

    - Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.

    - Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**. Per informazioni dettagliate sulle regole di traduzione, vedere [regole di traduzione in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**.

    - Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**.

    - Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

      > [!CAUTION]
      > Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.

15. Opzionale Associare e configurare **le regole di traduzione dei numeri** per il trunk. Le regole di traduzione si applicano al numero chiamato in una chiamata in uscita.

    - Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.

    - Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**. Per informazioni dettagliate sulle regole di traduzione, vedere [regole di traduzione in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**.

    - Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**.

    - Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

      > [!CAUTION]
      > Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.

16. Verificare che le regole di traduzione del trunk siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia verso l'alto o verso il basso.

    > [!IMPORTANT]
    > Skype for Business Server attraversa l'elenco delle regole di traduzione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato. Se si configura un trunk in modo che un numero composto possa corrispondere a più regole di traduzione, assicurarsi che le regole più restrittive siano ordinate al di sopra delle regole meno restrittive. Ad esempio, se è stata inclusa una regola di traduzione che corrisponde a qualsiasi numero di 11 cifre e a una regola di traduzione che corrisponde a solo numeri a 11 cifre che iniziano con + 1425, assicurarsi che la regola che corrisponde a qualsiasi numero di 11 cifre sia ordinata *sotto* quella più restrittiva. regola.

17. Al termine della configurazione del trunk, fare clic su **OK**.

18. Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.

## <a name="see-also"></a>Vedere anche

[Configurare un trunk con il bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Definizione delle regole di traduzione](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

