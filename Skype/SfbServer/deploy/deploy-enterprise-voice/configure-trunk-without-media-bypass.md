---
title: 'Skype for Business Server: Configurare un trunk senza bypass multimediale'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Riepilogo: configurare un trunk senza bypass multimediale abilitato per Skype for Business Server.'
---

# <a name="skype-for-business-server-configure-a-trunk-without-media-bypass"></a>Skype for Business Server: Configurare un trunk senza bypass multimediale

**Riepilogo:** Configurare un trunk senza bypass multimediale abilitato per Skype for Business Server.

Per configurare un trunk con il bypass multimediale disabilitato, attenersi alla procedura che segue. Se si desidera configurare un trunk con bypass multimediale abilitato, vedere [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md).

Una configurazione trunk, come quella descritta di seguito, raggruppa un set di parametri che vengono applicati ai trunk assegnati a questa configurazione trunk. Per una determinata configurazione trunk è possibile specificare un ambito globale (corrispondente a tutti i trunk che non presentano una configurazione di sito o di pool più specifica) o un ambito di sito o di pool. La configurazione trunk a livello di pool viene usata per definire un singolo trunk come ambito di una determinata configurazione trunk.

### <a name="to-configure-a-trunk-without-media-bypass"></a>Per configurare un trunk senza bypass multimediale

1. Aprire Skype for Business Server Pannello di controllo.

2. Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.

3. Nella pagina **Configurazione trunk** utilizzare uno dei metodi seguenti per configurare un trunk:

   - Fare doppio clic su un trunk esistente, ad esempio il trunk **Globale**, per visualizzare la finestra di dialogo **Modifica configurazione trunk**.

   - Fare clic su **Nuovo** e quindi selezionare un ambito per la nuova configurazione trunk:

   - **Trunk sito**: scegliere il sito per la configurazione trunk in **Selezionare un sito** e quindi fare clic su **OK**. Si noti che se è già stata creata una configurazione trunk per un sito, tale sito non verrà visualizzato in **Seleziona un sito**. La configurazione trunk verrà applicata a tutti i trunk presenti nel sito.

   - **Trunk pool**: scegliere il nome del trunk al quale si applica questa configurazione trunk in **Seleziona un servizio** e fare clic su **OK**. Questo trunk può essere il trunk radice o qualsiasi altro trunk definito in Generatore di topologie. Si noti che se è già stata creata una configurazione trunk per un trunk specifico, tale trunk non verrà visualizzato in **Seleziona un servizio**.

     > [!NOTE]
     > Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo. > Il **campo Nome** è precompilato con il nome del sito o del servizio associato alla configurazione trunk e non può essere modificato.

4. Selezionare una delle opzioni di **Livello di supporto crittografia** seguenti:

   - **Obbligatorio**: è necessario utilizzare la crittografia SRTP (Secure Realtime Transport Protocol) per proteggere il traffico tra Mediation Server e il gateway o PBX (Private Branch eXchange).

   - **Facoltativo**: la crittografia SRTP verrà utilizzata se supportata dal provider di servizi o dal produttore dell'apparecchiatura.

   - **Non supportato**: la crittografia SRTP non è supportata dal provider di servizi o dal produttore dell'apparecchiatura e pertanto non verrà utilizzata.

5. Verificare che la casella di controllo **Abilita bypass multimediale** sia deselezionata.

6. Selezionare la  casella di controllo Elaborazione multimediale centralizzata se è presente un punto di terminazione multimediale noto, ad esempio un gateway PSTN (Public Switched Telephone Network) in cui la terminazione multimediale ha lo stesso IP della terminazione della segnalazione. Deselezionare questa casella di controllo se il trunk non dispone di un media termination point noto.

7. Se il trunk peer supporta la ricezione di richieste SIP REFER dal Mediation Server, selezionare la casella di controllo Abilita invio **riferimento al gateway** .

8. (Facoltativo) Per abilitare il routing tra trunk, associare e configurare i record utilizzo PSTN a questa configurazione trunk. Gli utilizzi PSTN associati a questa configurazione trunk verranno applicati a tutte le chiamate in arrivo tramite il trunk che non proviene da un endpoint Skype for Business Server remoto. Per gestire i record utilizzo PSTN associati a una configurazione trunk, usare uno di questi metodi:

   - Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare i record da associare a questa configurazione trunk e quindi fare clic su **OK**.

   - Per rimuovere un record utilizzo PSTN da questa configurazione trunk, selezionare il record e fare clic su **Rimuovi**.

   - Per definire un nuovo record utilizzo PSTN e associarlo a questa configurazione trunk, eseguire le operazioni seguenti:

     a. Fare clic su **Nuova regola**.

     b. Nel campo **Nome** specificare un nome descrittivo univoco per il record.

     > [!NOTE]
     > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo **Nome** non può essere modificato.

     c. Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:

     - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**.

     - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.

     - Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

     - Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.

     d. Fare clic su **OK**.

   - Per modificare un record utilizzo PSTN già associato a questa configurazione trunk, eseguire le operazioni seguenti:

     a. Selezionare il record utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.

     b. Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:

     - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**.

     - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.

     - Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

     - Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**.

     c. Fare clic su **OK**.

     > [!IMPORTANT]
     > È importante associare i record di utilizzo PSTN in base al peer Mediation Server associato al trunk da configurare. Se il peer Mediation Server è un gateway PSTN o un session border controller (SBC), è consigliabile non associare la configurazione trunk a un record di utilizzo PSTN che instrada a una destinazione PSTN o a qualsiasi altro sistema downstream connesso tramite Skype for Business Server.

9. Organizzare i record utilizzo PSTN in modo da ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record di utilizzo PSTN e fare clic sulle frecce su o giù.

    > [!IMPORTANT]
    > L'ordine in cui i record utilizzo PSTN sono elencati nella configurazione trunk è significativo. Skype for Business Server l'elenco dall'alto verso il basso.

10. Per abilitare il bypass multimediale per i client protetti da NAT o firewall, selezionare **Abilita latch RTP** e un SBC che supporti il latch.

11. **Per abilitare l'invio** delle informazioni sulla cronologia delle chiamate al peer gateway del Mediation Server, è necessario selezionare Abilita cronologia chiamate di inoltro.

12. **Abilitare l'inoltro dei dati P-Asserted-Identity** per consentire l'inoltro delle informazioni sull'autore delle chiamate PAI tra il lato Mediation Server e il lato gateway (e viceversa), se presenti.

13. Per abilitare il failover rapido, selezionare **Abilita timer di failover del routing in uscita**. Il gateway associato a questo trunk può inviare una notifica entro 10 secondi dall'inizio dell'elaborazione di una chiamata in uscita. Se questa notifica non viene ricevuta dal Mediation Server, si verificherà il reindirizzamento a un altro trunk. Nelle reti in cui la latenza potrebbe ritardare il tempo di risposta o il gateway impiega più di 10 secondi per rispondere, è consigliabile disabilitare il failover rapido.

14. (Facoltativo) Associare e configurare le **Regole di conversione per il numero del chiamante** per il trunk. Tali regole sono applicabili al numero del chiamante per le chiamate in uscita.

    - Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.

    - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulle regole di conversione, vedere [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.

    - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**.

    - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

      > [!CAUTION]
      > Non associare regole di conversione a un trunk se nel peer trunk associato sono già configurate regole di conversione, poiché potrebbe verificarsi un conflitto tra le due regole.

15. (Facoltativo) Associare e configurare le **Regole di conversione per il numero chiamato** per il trunk. Tali regole sono applicabili al numero chiamato in una chiamata in uscita.

    - Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.

    - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulle regole di conversione, vedere [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.

    - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**.

    - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.

      > [!CAUTION]
      > Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.

16. Assicurarsi che le regole di conversione del trunk siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia su o giù.

    > [!IMPORTANT]
    > Skype for Business Server l'elenco delle regole di conversione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto. Se si configura un trunk in modo che un numero che viene composto possa soddisfare più regole di conversione, verificare che le regole più restrittive siano elencate al di sopra di quelle meno restrittive. Ad esempio, se è stata inclusa una regola di conversione che corrisponde a qualsiasi numero a 11 cifre e una regola di conversione che corrisponde solo a numeri a 11 cifre che iniziano con +1425, assicurarsi che la regola corrispondente a qualsiasi numero a 11 cifre  sia ordinata sotto la regola più restrittiva.

17. Dopo aver terminato la configurazione del trunk, fare clic su **OK**.

18. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.

    > [!NOTE]
    > Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando **Salva tutto** per pubblicare la modifica apportata alla configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.

## <a name="see-also"></a>Vedere anche

[Configurare un trunk con bypass multimediale in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Definizione delle regole di conversione](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)