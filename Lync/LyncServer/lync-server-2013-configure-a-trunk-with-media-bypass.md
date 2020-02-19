---
title: 'Lync Server 2013: configurare un trunk con bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fa619262aee2b1342dce6f211eec7ff31aabe62
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a>Configurare un trunk con bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-07_

Seguire questa procedura per configurare un trunk con bypass multimediale abilitato. Per configurare un trunk con bypass multimediale disabilitato, vedere [Configure a Trunk Without Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md). La funzionalità bypass multimediale è utile se si desidera ridurre il numero dei Mediation Server distribuiti. Un pool Mediation Server viene in genere distribuito in un sito centrale e controlla i gateway nei siti di succursale. Abilitando il bypass multimediale, gli elementi multimediali per chiamate PSTN da client dei siti di succursale possono attraversare direttamente i gateway di tali siti. Lync Server 2013 le route delle chiamate in uscita e i criteri VoIP aziendale devono essere adeguatamente configurati in modo che le chiamate PSTN dai client in un sito di succursale vengano instradate al gateway appropriato.

Si consiglia di abilitare il bypass multimediale. Tuttavia, prima di abilitare il bypass multimediale su un trunk SIP, verificare che il provider trunk SIP qualificato supporti il bypass multimediale ed è in grado di soddisfare i requisiti per l'attivazione corretta dello scenario. In particolare, il provider deve disporre degli indirizzi IP dei server nella rete interna dell'organizzazione. Se il provider non è in grado di supportare questo scenario, non sarà possibile utilizzare il bypass multimediale. Per informazioni dettagliate, vedere [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella documentazione relativa alla pianificazione.

<div>


> [!NOTE]  
> Il bypass multimediale non interagisce con tutti i gateway PSTN (Public Switched Telephone Network), IP-PBX e Session Border Controller (SBC). Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

Una configurazione trunk come descritto di seguito raggruppa un insieme di parametri applicati ai trunk assegnati alla configurazione del trunk. Per una determinata configurazione trunk è possibile specificare un ambito globale (corrispondente a tutti i trunk che non presentano una configurazione di sito o di pool più specifica) o un ambito di sito o di pool. La configurazione trunk a livello di pool viene usata per definire un singolo trunk come ambito di una determinata configurazione trunk.

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a>Per configurare un trunk con bypass multimediale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.

4.  Nella pagina **Configurazione trunk** utilizzare uno dei metodi seguenti per configurare un trunk:
    
      - Fare doppio clic su un trunk esistente, ad esempio il trunk **Globale**, per visualizzare la finestra di dialogo **Modifica configurazione trunk**.
    
      - Fare clic su **Nuovo** e quindi selezionare un ambito per la nuova configurazione trunk:
        
          - **Trunk del sito:** Scegliere il sito per la configurazione del trunk da **Seleziona un sito**e quindi fare clic su **OK**. Si noti che se è già stata creata una configurazione trunk per un sito, tale sito non verrà visualizzato in **Seleziona un sito**. La configurazione trunk verrà applicata a tutti i trunk presenti nel sito.
        
          - **Trunk del pool:** Scegliere il nome del trunk a cui si applica la configurazione del trunk. Questo trunk può essere il trunk radice o qualsiasi trunk aggiuntivo definito in Generatore di topologie. Da **Seleziona un servizio**, fare clic su **OK**. Si noti che se è già stata creata una configurazione trunk per un trunk specifico, tale trunk non verrà visualizzato in **Seleziona un servizio**.
    
    <div>
    

    > [!NOTE]  
    > Dopo aver selezionato l'ambito della configurazione trunk, non è possibile modificarlo.<BR>Il campo <STRONG>Nome</STRONG> è già compilato con il nome del sito o del servizio associato alla configurazione trunk e non è possibile modificarlo.

    
    </div>

5.  Specificare un valore nelle **finestre di dialogo massime iniziali supportate**. Questo è il numero massimo di risposte a forcella che un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un session border controller (SBC) di ITSP può ricevere a un invito inviato al Mediation Server. Il valore predefinito è 20.
    
    <div>
    

    > [!NOTE]  
    > Prima di modificare questo valore, consultare il provider di servizi o il produttore delle apparecchiature per informazioni più dettagliate sulle capacità del sistema in uso.

    
    </div>

6.  Selezionare una delle opzioni di **Livello di supporto crittografia** seguenti:
    
      - **Obbligatorio:** È necessario utilizzare la crittografia SRTP (Secure Real-Time Transport Protocol) per proteggere il traffico tra il Mediation Server e il gateway o il PBX (Private Branch Exchange).
    
      - **Facoltativo:** La crittografia SRTP verrà utilizzata se il provider di servizi o il produttore di apparecchiature lo supporta.
    
      - **Non supportato:** La crittografia SRTP non è supportata dal provider di servizi o dal produttore dell'attrezzatura e pertanto non verrà utilizzata.

7.  Selezionare la casella di controllo **Abilita bypass multimediale** se si desidera che gli elementi multimediali ignorino il Mediation Server per l'elaborazione da parte del trunk peer.
    
    <div>
    

    > [!IMPORTANT]  
    > Per un corretto funzionamento del bypass multimediale, è necessario che il gateway PSTN, il sistema IP-PBX o il Session Border Controller supporti determinate funzionalità. Per informazioni dettagliate, vedere <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in Lync Server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

8.  Selezionare la casella di controllo **Elaborazione multimediale centralizzata** se esiste un punto di terminazione multimediale noto, ad esempio un gateway PSTN in cui la terminazione multimediale ha lo stesso IP della terminazione di segnalazione. Deselezionare la casella di controllo se il trunk non dispone di un punto di terminazione multimediale noto.

9.  Se il peer trunk supporta la ricezione di richieste SIP REFER dal Mediation Server, selezionare la casella **di controllo Abilita l'invio di fare riferimento al gateway** .
    
    <div>
    

    > [!NOTE]  
    > Se si disabilita questa opzione mentre è selezionata l'opzione <STRONG>Abilita bypass multimediale</STRONG> saranno necessarie ulteriori impostazioni. Se il trunk peer non supporta la ricezione di richieste SIP REFER dal Mediation Server ed è abilitato il bypass multimediale, sarà inoltre necessario eseguire il cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> per disabilitare RTCP per le chiamate attive e in attesa in modo da supportare le condizioni appropriate per il bypass multimediale. Per informazioni dettagliate, vedere la documentazione di <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> .<BR>In alternativa, è possibile selezionare <STRONG>Abilita fare riferimento utilizzando un controllo delle chiamate di terze parti</STRONG> se si desidera che le chiamate trasferite vengano ignorate tramite il supporto e il gateway non supporta le richieste SIP REFER.

    
    </div>

10. (Facoltativo) Per abilitare il routing tra trunk, associare e configurare i record utilizzo PSTN a questa configurazione trunk. Gli utilizzi PSTN associati alla configurazione trunk verranno applicati per tutte le chiamate in arrivo tramite il trunk che non è originato da un endpoint Lync. Per gestire i record utilizzo PSTN associati a una configurazione trunk, usare uno di questi metodi:
    
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

11. Organizzare i record utilizzo PSTN in modo da ottenere prestazioni ottimali. Per modificare la posizione di un record nell'elenco, selezionare il record utilizzo PSTN e fare clic sulle frecce verso l'alto o verso il basso.
    
    <div>
    

    > [!IMPORTANT]  
    > L'ordine in cui i record utilizzo PSTN sono elencati nella configurazione trunk è significativo. Lync Server attraversa l'elenco dall'alto verso il basso.

    
    </div>

12. **Abilitare il latching RTP** deve essere selezionato per abilitare il bypass multimediale per i client dietro una NAT (Network Address Translation) o un firewall e un SBC che supporta l'aggancio.

13. **Abilitare la cronologia delle chiamate inoltrate** per consentire l'invio delle informazioni sulla cronologia delle chiamate al peer gateway del Mediation Server.

14. **Abilitare l'inoltro dei dati di identità p-Asserted-Identity** per abilitare l'inoltro delle informazioni sull'originatore delle chiamate di p-Asserted-Identity (PAI) tra il lato Mediation Server e il lato gateway (e viceversa), se presente.

15. Per abilitare il failover rapido, selezionare **Abilita timer di failover del routing in uscita**. Il gateway associato a questo trunk può inviare una notifica entro 10 secondi dall'inizio dell'elaborazione di una chiamata in uscita. Se la notifica non viene ricevuta dal Mediation Server, il reinstradamento a un altro trunk si verificherà. Nelle reti in cui la latenza potrebbe ritardare il tempo di risposta o il gateway impiega più di 10 secondi per rispondere, è consigliabile disabilitare il failover rapido.

16. (Facoltativo) Associare e configurare le **Regole di conversione per il numero del chiamante** per il trunk. Tali regole sono applicabili al numero del chiamante per le chiamate in uscita.
    
      - Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.
    
      - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.
    
    <div>
    

    > [!WARNING]  
    > Non associare regole di conversione a un trunk se nel peer trunk associato sono già configurate regole di conversione, poiché potrebbe verificarsi un conflitto tra le due regole.

    
    </div>

17. (Facoltativo) Associare e configurare le **Regole di conversione per il numero chiamato** per il trunk. Tali regole sono applicabili al numero chiamato in una chiamata in uscita.
    
      - Per scegliere una o più regole da un elenco di tutte le regole di conversione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**. In **Seleziona regole di conversione** fare clic sulle regole da associare al trunk e quindi su **OK**.
    
      - Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**. Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**. Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.
    
      - Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**. Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.
    
    <div>
    

    > [!WARNING]  
    > Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel peer trunk associato, perché le due regole potrebbero essere in conflitto.

    
    </div>

18. Verificare che le regole di conversione del trunk siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e fare clic sulla freccia su o giù.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 attraversa l'elenco delle regole di conversione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto. Se si configura un trunk in modo che un numero che viene composto possa soddisfare più regole di conversione, verificare che le regole più restrittive siano elencate al di sopra di quelle meno restrittive. Se ad esempio sono state incluse una regola di conversione per qualsiasi numero di 11 cifre e una regola di conversione solo per i numeri di 11 cifre che iniziano con +1425, verificare che la regola per i numeri di 11 cifre sia elencata <EM>al di sotto</EM> della regola più restrittiva.

    
    </div>

19. Dopo aver terminato la configurazione del trunk, fare clic su **OK**.

20. Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.
    
    <div>
    

    > [!NOTE]  
    > Ogni volta che si crea o si modifica una configurazione trunk, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.

    
    </div>

Dopo aver configurato il trunk, continuare a configurare il bypass multimediale scegliendo tra le opzioni di bypass multimediale globale, come descritto in [Global Media Bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[Configurare il bypass multimediale in Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

