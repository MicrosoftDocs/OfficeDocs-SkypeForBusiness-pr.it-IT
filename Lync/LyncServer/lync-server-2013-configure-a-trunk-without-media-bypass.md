---
title: 'Lync Server 2013: configurare un trunk senza bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6508fe88a585c22b9936e787be2ee99b8f9b7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>Configurare un trunk senza bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

Se si vuole configurare un trunk con il bypass multimediale disabilitato, eseguire le operazioni seguenti. Se si vuole configurare un trunk con il bypass multimediale abilitato, vedere [configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Una configurazione trunk, come descritto di seguito, raggruppa un set di parametri applicati ai trunk assegnati alla configurazione del trunk. Una particolare configurazione trunk può essere portata a livello globale (per tutti i trunk che non dispongono di una configurazione di sito o di pool più specifica) o di un sito o di un pool. La configurazione del trunk a livello di pool viene usata per l'ambito di una configurazione trunk specifica in un singolo trunk.

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>Per configurare un trunk senza bypass multimediale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **configurazione trunk**.

4.  Nella pagina **trunk Configuration** usare uno dei metodi seguenti per configurare un trunk:
    
      - Fare doppio clic su un trunk esistente, ad esempio il trunk **globale** , per visualizzare la finestra di dialogo **modifica configurazione trunk** .
    
      - Fare clic su **nuovo**e quindi selezionare un ambito per la nuova configurazione trunk:
        
          - **Trunk sito:** Scegliere il sito per questa configurazione trunk in **selezionare un sito** e quindi fare clic su **OK**. Tieni presente che se è già stata creata una configurazione trunk per un sito, il sito non viene visualizzato in **Seleziona un sito**. Questa configurazione trunk verrà applicata a tutti i trunk nel sito.
        
          - **Trunk pool:** Scegliere il nome del trunk a cui si applica la configurazione del trunk in **selezionare un servizio** e fare clic su **OK**. Questo trunk può essere il trunk radice o altri trunk definiti in Generatore di topologia. Tieni presente che se è già stata creata una configurazione trunk per un trunk specifico, il trunk non viene visualizzato in **Seleziona un servizio**.
    
    <div>
    

    > [!NOTE]  
    > Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo.<BR>Il campo <STRONG>nome</STRONG> viene prepopolato con il nome del sito o del servizio associato alla configurazione del trunk e non può essere modificato.

    
    </div>

5.  Selezionare una delle opzioni seguenti per il **livello di supporto della crittografia** :
    
      - **Obbligatorio:** Per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange), è necessario usare la crittografia SRTP (Secure Real Time Transport Protocol).
    
      - **Facoltativo:** La crittografia SRTP verrà usata se il provider di servizi o il produttore di attrezzature lo supporta.
    
      - **Non supportato:** La crittografia SRTP non è supportata dal provider di servizi o dal produttore di attrezzature e quindi non verrà usata.

6.  Assicurarsi che la casella di controllo **Abilita esclusione multimediale** sia deselezionata.

7.  Selezionare la casella di controllo **elaborazione multimediale centralizzata** se è presente un punto di interruzione del contenuto multimediale noto, ad esempio un gateway PSTN (Public Switched Telephone Network) in cui la terminazione multimediale ha lo stesso IP della terminazione di segnalazione. Deselezionare questa casella di controllo se il trunk non ha un punto di interruzione multimediale noto.

8.  Se il peer trunk supporta la ricezione delle richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Consenti invio di riferimento al gateway** .

9.  Opzionale Per abilitare il routing tra trunk, associa e configura i record di utilizzo PSTN alla configurazione del trunk. Gli usi PSTN associati alla configurazione del trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk non proveniente da un endpoint Lync. Per gestire i record di utilizzo PSTN associati a una configurazione trunk, usare uno dei metodi seguenti:
    
      - Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare i record che si desidera associare alla configurazione del trunk e quindi fare clic su **OK**.
    
      - Per rimuovere un record di utilizzo PSTN dalla configurazione del trunk, selezionare il record e fare clic su **Rimuovi**.
    
      - Per definire un nuovo record di utilizzo PSTN e associarlo alla configurazione del trunk, eseguire le operazioni seguenti:
        
        1.  Fare clic su **nuovo**.
        
        2.  Nel campo **nome** specificare un nome descrittivo per il record univoco.
            
            <div>
            

            > [!NOTE]  
            > Il nome del record utilizzo PSTN deve essere univoco all'interno della distribuzione VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>nome</STRONG> non può essere modificato.

            
            </div>
        
        3.  Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:
            
              - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**.
            
              - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
            
              - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Fare clic su **OK**.
    
      - Per modificare un record di utilizzo PSTN già associato alla configurazione del trunk, eseguire le operazioni seguenti:
        
        1.  Selezionare il record di utilizzo PSTN che si vuole modificare e fare clic su **Mostra dettagli**.
        
        2.  Usare uno dei metodi seguenti per associare e configurare le route per il record di utilizzo PSTN:
            
              - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. Evidenziare le route da associare al record di utilizzo PSTN e fare clic su **OK**.
            
              - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
            
              - Per definire una nuova route e associarla al record di utilizzo PSTN, fare clic su **nuovo**. Per informazioni dettagliate, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Per modificare una route associata a questo record di utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Fare clic su **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > È importante associare i record di utilizzo PSTN in base al peer di Mediation Server associato al trunk configurato. Se il peer di Mediation Server è un gateway PSTN o un SBC (Session Border Controller), è consigliabile che la configurazione trunk non sia associata a un record di utilizzo PSTN che si indirizza a una destinazione PSTN o a qualsiasi altro sistema downstream connesso tramite Lync Server.

    
    </div>

10. Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce in su o in giù.
    
    <div>
    

    > [!IMPORTANT]  
    > L'ordine in cui sono elencati i record di utilizzo PSTN nella configurazione trunk è significativo. Lync Server attraversa l'elenco dall'alto verso il basso.

    
    </div>

11. **Abilitare il latching RTP** deve essere selezionato per consentire l'esclusione di elementi multimediali per i client dietro un NAT o un firewall e un SBC che supporta il blocco.

12. **Abilitare la cronologia delle chiamate in avanti** deve essere selezionata per consentire l'invio di informazioni sulla cronologia delle chiamate al peer del gateway del Mediation Server.

13. **Abilita inoltro P-asserzione-i dati di identità** devono essere selezionati per consentire l'inoltro delle informazioni sull'originatore delle chiamate di Pai tra il lato Mediation Server e il lato gateway (e viceversa), quando presenti.

14. **Abilitare il timer di failover del routing in uscita** deve essere selezionato per consentire il failover veloce. Il gateway associato a questo trunk può dare notifica entro 10 secondi che sta elaborando una chiamata in uscita. La reinstradazione a un altro trunk si verificherà se la notifica non viene ricevuta dal Mediation Server. Nelle reti in cui la latenza può ritardare il tempo di risposta o il gateway richiede più di 10 secondi per rispondere, il failover veloce deve essere disabilitato.

15. Opzionale Associa e configura le **regole di traduzione del numero chiamante** per il trunk. Queste regole di traduzione si applicano al numero chiamante per le chiamate in uscita
    
      - Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.
    
      - Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. Opzionale Associare e configurare **le regole di traduzione dei numeri** per il trunk. Le regole di traduzione si applicano al numero chiamato in una chiamata in uscita.
    
      - Per scegliere una o più regole da un elenco di tutte le regole di traduzione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**. In **Seleziona regole di traduzione**fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.
    
      - Per definire una nuova regola di traduzione e associarla al trunk, fare clic su **nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per modificare una regola di traduzione già associata al trunk, fare clic sul nome della regola e quindi fare clic su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per copiare una regola di traduzione esistente da usare come punto di partenza per la definizione di una nuova regola, fare clic sul nome della regola e scegliere **copia**e quindi fare clic su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di traduzione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Per rimuovere una regola di traduzione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.
    
    <div>
    

    > [!WARNING]  
    > Non associare regole di traduzione a un trunk se sono state configurate regole di traduzione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.

    
    </div>

17. Verificare che le regole di traduzione del trunk siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia verso l'alto o verso il basso.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server attraversa l'elenco delle regole di traduzione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato. Se si configura un trunk in modo che un numero composto possa corrispondere a più regole di traduzione, assicurarsi che le regole più restrittive siano ordinate al di sopra delle regole meno restrittive. Se ad esempio è stata inclusa una regola di traduzione che corrisponde a qualsiasi numero di 11 cifre e a una regola di traduzione che corrisponde a solo numeri a 11 cifre che iniziano con + 1425, assicurarsi che la regola che corrisponde a qualsiasi numero di 11 cifre sia ordinata <EM>sotto</EM> la regola più restrittiva.

    
    </div>

18. Al termine della configurazione del trunk, fare clic su **OK**.

19. Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

