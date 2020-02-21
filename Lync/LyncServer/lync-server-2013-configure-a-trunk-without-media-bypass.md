---
title: 'Lync Server 2013: configurare un trunk senza bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7216b6c3003ab30a31a9181e11d725c4827f0584
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>Configurare un trunk senza bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

Per configurare un trunk con il bypass multimediale disabilitato, attenersi alla procedura che segue. Se si desidera configurare un trunk con bypass multimediale abilitato, vedere [Configure a Trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Una configurazione trunk, come quella descritta di seguito, raggruppa un set di parametri che vengono applicati ai trunk assegnati a questa configurazione trunk. Per una determinata configurazione trunk è possibile specificare un ambito globale (corrispondente a tutti i trunk che non presentano una configurazione di sito o di pool più specifica) o un ambito di sito o di pool. La configurazione trunk a livello di pool viene usata per definire un singolo trunk come ambito di una determinata configurazione trunk.

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>Per configurare un trunk senza bypass multimediale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.

4.  Nella pagina **Configurazione trunk** utilizzare uno dei metodi seguenti per configurare un trunk:
    
      - Fare doppio clic su un trunk esistente, ad esempio il trunk **Globale**, per visualizzare la finestra di dialogo **Modifica configurazione trunk**.
    
      - Fare clic su **Nuovo** e quindi selezionare un ambito per la nuova configurazione trunk:
        
          - **Trunk del sito:** Scegliere il sito per la configurazione del trunk in **Seleziona un sito** e quindi fare clic su **OK**. Si noti che se è già stata creata una configurazione trunk per un sito, tale sito non verrà visualizzato in **Seleziona un sito**. La configurazione trunk verrà applicata a tutti i trunk presenti nel sito.
        
          - **Trunk del pool:** Scegliere il nome del trunk a cui si applica la configurazione del trunk in **Seleziona un servizio** e quindi fare clic su **OK**. Questo trunk può essere il trunk radice o qualsiasi trunk aggiuntivo definito in Generatore di topologie. Si noti che se è già stata creata una configurazione trunk per un trunk specifico, tale trunk non verrà visualizzato in **Seleziona un servizio**.
    
    <div>
    

    > [!NOTE]  
    > Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo.<BR>Il campo <STRONG>Nome</STRONG> è già compilato con il nome del sito o del servizio associato alla configurazione trunk e non è possibile modificarlo.

    
    </div>

5.  Selezionare una delle opzioni di **Livello di supporto crittografia** seguenti:
    
      - **Obbligatorio:** È necessario utilizzare la crittografia SRTP (Secure Real-Time Transport Protocol) per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange).
    
      - **Facoltativo:** La crittografia SRTP verrà utilizzata se il provider di servizi o il produttore di apparecchiature lo supporta.
    
      - **Non supportato:** La crittografia SRTP non è supportata dal provider di servizi o dal produttore dell'attrezzatura e pertanto non verrà utilizzata.

6.  Verificare che la casella di controllo **Abilita bypass multimediale** sia deselezionata.

7.  Selezionare la casella di controllo **Elaborazione multimediale centralizzata** se è presente un media termination point noto, ad esempio un gateway PSTN (Public Switched Telephone Network) in cui l'IP della terminazione multimediale e quello della terminazione dei segnali coincidono. Deselezionare questa casella di controllo se il trunk non dispone di un media termination point noto.

8.  Se il peer trunk supporta la ricezione di richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Abilita l'invio di fare riferimento al gateway** .

9.  (Facoltativo) Per abilitare il routing tra trunk, associare e configurare i record utilizzo PSTN a questa configurazione trunk. Gli utilizzi PSTN associati alla configurazione trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk che non è originato da un endpoint Lync. Per gestire i record utilizzo PSTN associati a una configurazione trunk, usare uno di questi metodi:
    
      - Per selezionare uno o più record da un elenco di tutti i record di utilizzo PSTN disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare i record da associare a questa configurazione trunk e quindi fare clic su **OK**.
    
      - Per rimuovere un record utilizzo PSTN da questa configurazione trunk, selezionare il record e fare clic su **Rimuovi**.
    
      - Per definire un nuovo record utilizzo PSTN e associarlo a questa configurazione trunk, eseguire le operazioni seguenti:
        
        1.  Fare clic su **Nuovo**.
        
        2.  Nel campo **Nome** specificare un nome descrittivo univoco per il record.
            
            <div>
            

            > [!NOTE]  
            > Il nome del record di utilizzo PSTN deve essere univoco all'interno della distribuzione di VoIP aziendale. Dopo il salvataggio del record, il campo <STRONG>Nome</STRONG> non può essere modificato.

            
            </div>
        
        3.  Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:
            
              - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**.
            
              - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
            
              - Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**. Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Fare clic su **OK**.
    
      - Per modificare un record utilizzo PSTN già associato a questa configurazione trunk, eseguire le operazioni seguenti:
        
        1.  Selezionare il record utilizzo PSTN da modificare e fare clic su **Mostra dettagli**.
        
        2.  Per associare e configurare le route per questo record utilizzo PSTN, usare uno dei metodi seguenti:
            
              - Per selezionare una o più route dall'elenco di tutte le route disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. Evidenziare le route da associare a questo record utilizzo PSTN e fare clic su **OK**.
            
              - Per rimuovere una route dal record utilizzo PSTN, selezionare la route e fare clic su **Rimuovi**.
            
              - Per definire una nuova route e associarla a questo record utilizzo PSTN, fare clic su **Nuovo**. Per informazioni dettagliate, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Per modificare una route associata a questo record utilizzo PSTN, selezionare la route e fare clic su **Mostra dettagli**. Per ulteriori informazioni, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Fare clic su **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > È importante associare i record di utilizzo PSTN in base al peer Mediation Server associato al trunk configurato. Se il peer Mediation Server è un gateway PSTN o un session border controller (SBC), è consigliabile che la configurazione trunk non sia associata a un record di utilizzo PSTN che si incammini su una destinazione PSTN o su qualsiasi altro sistema downstream connesso tramite Lync Server.

    
    </div>

10. Organizzare i record utilizzo PSTN in modo da ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce verso l'alto o verso il basso.
    
    <div>
    

    > [!IMPORTANT]  
    > L'ordine in cui i record utilizzo PSTN sono elencati nella configurazione trunk è significativo. Lync Server attraversa l'elenco dall'alto verso il basso.

    
    </div>

11. Per abilitare il bypass multimediale per i client protetti da NAT o firewall, selezionare **Abilita latch RTP** e un SBC che supporti il latch.

12. **Abilitare la cronologia delle chiamate inoltrate** per consentire l'invio delle informazioni sulla cronologia delle chiamate al peer gateway del Mediation Server.

13. Per abilitare l'inoltro delle informazioni sull'originatore delle chiamate PAI tra il lato Mediation Server e il lato gateway (e viceversa), è necessario selezionare **i dati P-Asserted-Identity** .

14. Per abilitare il failover rapido, selezionare **Abilita timer di failover del routing in uscita**. Il gateway associato a questo trunk può inviare una notifica entro 10 secondi dall'inizio dell'elaborazione di una chiamata in uscita. Se la notifica non viene ricevuta dal Mediation Server, il reinstradamento a un altro trunk si verificherà. Nelle reti in cui la latenza potrebbe ritardare il tempo di risposta o il gateway impiega più di 10 secondi per rispondere, è consigliabile disabilitare il failover rapido.

15. (Facoltativo) Associare e configurare le **Regole di conversione per il numero del chiamante** per il trunk. Tali regole sono applicabili al numero del chiamante per le chiamate in uscita.
    
      - Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.
    
      - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" />Nota sulla sicurezza:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Non associare regole di conversione a un trunk se nel peer trunk associato sono già configurate regole di conversione, poiché potrebbe verificarsi un conflitto tra le due regole.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. (Facoltativo) Associare e configurare le **Regole di conversione per il numero chiamato** per il trunk. Tali regole sono applicabili al numero chiamato in una chiamata in uscita.
    
      - Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.
    
      - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.
    
    <div>
    

    > [!WARNING]  
    > Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.

    
    </div>

17. Verificare che le regole di conversione del trunk siano disposte nell'ordine corretto. Per cambiare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia verso l'alto o verso il basso.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server attraversa l'elenco delle regole di conversione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto. Se si configura un trunk in modo che un numero che viene composto possa soddisfare più regole di conversione, verificare che le regole più restrittive siano elencate al di sopra di quelle meno restrittive. Se ad esempio sono state incluse una regola di conversione per qualsiasi numero di 11 cifre e una regola di conversione solo per i numeri di 11 cifre che iniziano con +1425, verificare che la regola per i numeri di 11 cifre sia elencata <EM>al di sotto</EM> della regola più restrittiva.

    
    </div>

18. Dopo aver terminato la configurazione del trunk, fare clic su **OK**.

19. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

