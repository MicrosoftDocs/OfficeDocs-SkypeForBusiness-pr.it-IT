---
title: 'Lync Server 2013: configurare la messaggistica unificata in Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

Questo argomento descrive come configurare la messaggistica unificata di Exchange in un server di Microsoft Exchange per l'uso con Enterprise Voice.

<div>


> [!NOTE]  
> Gli esempi di cmdlet in questo argomento includono la sintassi per la versione di Exchange 2007 di Exchange Management Shell. Se si esegue Exchange 2010 o Exchange 2013, vedere la documentazione appropriata come a cui si fa riferimento.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Per configurare un server che esegua la messaggistica unificata di Exchange Server

1.  Creare un dial plan (URI) Uniform Resource Identifier (SIP) di messaggistica unificata per ogni profilo della posizione della segreteria aziendale. Se si sceglie di usare Exchange Management Console, creare un nuovo dial plan con l'impostazione di sicurezza **protetta (preferita)**.
    
    <div>
    

    > [!WARNING]  
    > Se si imposta il valore dell'impostazione di sicurezza su <STRONG>SIP Secured</STRONG> per richiedere la crittografia solo per il traffico SIP, come raccomandato in precedenza, tenere presente che questa impostazione di sicurezza in un dial plan è insufficiente se il pool Front-End è configurato per richiedere la crittografia, quindi il pool richiede la crittografia per il traffico SIP e RTP. Quando le impostazioni di sicurezza del dial plan e del pool non sono compatibili, tutte le chiamate alla messaggistica unificata di Exchange dal pool Front-End avranno esito negativo, con un errore che indica che è presente un'impostazione di sicurezza non compatibile.

    
    </div>
    
    Se si usa Exchange Management Shell, digitare:
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Per informazioni dettagliate, vedere:
    
      - Per Office Communications Server 2007, vedere "come creare un dial plan URI SIP di messaggistica unificata" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) e "New-UMDialplan: Guida di Exchange 2007" [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)all'indirizzo.
    
      - Per Exchange 2010, vedere "creare un dial plan di messaggistica unificata" in [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) e "New-UMDialplan: Guida di [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)Exchange 2010" all'indirizzo.
    
      - Per Exchange 2013, vedere la pagina relativa alla [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)messaggistica unificata.
    
    <div>
    

    > [!NOTE]  
    > Se si seleziona un livello di sicurezza di <STRONG>SIPSecured</STRONG> o <STRONG>protetto</STRONG> , dipende dal fatto che il protocollo SRTP (Secure Real Time Transport Protocol) viene attivato o disattivato per la crittografia media. Per l'integrazione di Lync Server 2010 con la messaggistica unificata di Exchange, questo deve corrispondere al livello di crittografia nella configurazione multimediale di Lync Server. La configurazione multimediale di Lync Server può essere visualizzata eseguendo il cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> . Per informazioni dettagliate, vedere Get-CsMediaConfiguration nella documentazione di Lync Server Management Shell.<BR>Per informazioni dettagliate sulla selezione dell'impostazione di sicurezza VoIP appropriata, vedere <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo di distribuzione per l'integrazione di messaggistica unificata locale e Lync Server 2013</A>.

    
    </div>

2.  Eseguire il cmdlet seguente per ottenere il nome di dominio completo (FQDN) per ogni dial plan di messaggistica unificata:
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Per informazioni dettagliate, vedere:
    
      - Per Exchange 2007, vedere "Get-UMDialplan: Guida di Exchange 2007" [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)all'indirizzo.
    
      - Per Exchange 2010, vedere "Get-UMDialplan: Guida di Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)all'indirizzo.
    
      - Per Exchange 2013, vedere la pagina relativa alla [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)messaggistica unificata.

3.  Registrare il nome del dial plan di ogni dial plan di messaggistica unificata. A seconda della versione di Exchange Server in uso, potrebbe essere necessario usare l'FQDN di ogni nome di dial plan in un secondo momento come nome del dial plan di Lync Server corrispondente di ogni dial plan di messaggistica unificata, in modo che i nomi dei dial plan corrispondano.
    
    <div>
    

    > [!NOTE]  
    > I nomi di dial plan di Lync Server devono corrispondere ai nomi di dial plan di messaggistica unificata solo se il dial plan di messaggistica unificata è in esecuzione in una versione di Exchange <EM>precedente</EM> a Exchange 2010 SP1.

    
    </div>

4.  Aggiungere il dial plan al server che gestisce la messaggistica unificata di Exchange nel modo seguente:
    
      - Se si sceglie di usare Exchange Management Console, è possibile aggiungere il dial plan dalla finestra delle proprietà per il server. Per istruzioni specifiche, vedere la documentazione del prodotto Exchange Server.
        
        Per Exchange 2007, vedere "come aggiungere un server di messaggistica unificata a un dial plan" [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).
        
        Per Exchange 2010, vedere la pagina relativa alla [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)visualizzazione o alla configurazione delle proprietà di un server di messaggistica unificata.
        
        Per Exchange 2013, vedere la pagina relativa alla [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)messaggistica unificata.
    
      - Se si usa Exchange Management Shell, eseguire la procedura seguente per ogni server Messaggistica unificata di Exchange:
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Prima di eseguire il passaggio seguente, verificare che tutti gli utenti di VoIP aziendale siano stati configurati con una cassetta postale di Exchange Server.<BR>Per Exchange 2007, vedere la raccolta TechNet di <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>exchange server 2007.<BR>Per Exchange 2010, vedere la raccolta TechNet di <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>exchange server 2010.<BR>Quando si specifica un criterio di cassetta postale per ogni dial plan creato nel passaggio 1, selezionare il criterio predefinito o quello creato.

    
    </div>

5.  Passare agli \<script di directory\>\\di installazione di Exchange e quindi, se Exchange è distribuito in una singola foresta, digitare:
    ```console
    exchucutil.ps1
    ```
    In alternativa, se Exchange è distribuito in più foreste, digitare:
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    dove FQDN foresta specifica la foresta in cui è distribuito Lync Server.
    
    Se si hanno uno o più dial plan di messaggistica unificata associati a più gateway IP, continuare con il passaggio 6. Se i piani di chiamata sono associati solo a un singolo gateway IP, saltare il passaggio 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Assicurarsi di riavviare il servizio <STRONG>front-end di Lync Server</STRONG> (RtcSrv. exe) <EM>dopo</EM> l'esecuzione di exchucutil. ps1. In caso contrario, Lync Server non rileverà la messaggistica unificata nella topologia.

    
    </div>

6.  Se si usa Exchange Management Shell o Exchange Management Console, disabilitare le chiamate in uscita per tutti i gateway IP associati a ogni piano di chiamata.
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio è necessario per verificare che le chiamate in uscita dal server che gestisce la messaggistica unificata di Exchange Server a utenti esterni (ad esempio, come nel caso degli scenari di riproduzione su telefono) attraversino in modo affidabile il firewall aziendale.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Quando si seleziona il gateway IP di messaggistica unificata tramite cui consentire le chiamate in uscita, scegliere quello che probabilmente gestirà la maggior parte del traffico. Non consentire il traffico in uscita tramite un gateway IP che si connette a un pool di amministratori di Lync Server. Evitare inoltre i pool in un altro sito centrale o in un sito di succursale. Puoi usare uno dei metodi seguenti per bloccare le chiamate in uscita passando da un gateway IP:

    
    </div>
    
      - Se si usa Exchange Management Shell, disabilitare ogni gateway IP eseguendo il comando seguente:
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Per Exchange 2007, vedere "Set-UMIPGateway: Guida di Exchange 2007" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)all'indirizzo.
        
        Per Exchange 2010, vedere "Set-UMIPGateway: Guida di Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)all'indirizzo.
    
      - Se si usa Exchange Management Console, deselezionare la casella di controllo **Consenti chiamate in uscita tramite il gateway IP** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se il dial plan URI SIP di messaggistica unificata è associato solo a un singolo gateway IP, non impedire le chiamate in uscita tramite il gateway.

    
    </div>

7.  Creare un operatore automatico di messaggistica unificata per ogni dial plan di Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Non includere spazi nel nome dell'operatore automatico.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Per informazioni dettagliate, vedere:
    
      - Per Exchange 2007, vedere "New-UMAutoAttendant: Guida di Exchange 2007" [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)all'indirizzo.
    
      - Per Exchange 2010, vedere "New-UMAutoAttendant: Guida di Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)all'indirizzo.
    
    Il passaggio seguente deve essere eseguito per ogni utente dopo aver abilitato gli utenti di Lync Server per VoIP aziendale e conoscere gli URI SIP.

8.  Associare gli utenti di messaggistica unificata di Exchange (ognuno dei quali deve essere configurato con una casella di posta di Exchange) con il dial plan di messaggistica unificata e creare un URI SIP per ogni utente.
    
    <div>
    

    > [!NOTE]  
    > L' <STRONG>parametro SIPResourceIdentifier</STRONG> nell'esempio seguente deve essere l'indirizzo SIP dell'utente di Lync Server.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Per informazioni dettagliate, vedere:
    
      - Per Exchange 2007, vedere "Enable-UMMailbox: Guida di Exchange 2007" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)all'indirizzo.
    
      - Per Exchange 2010, vedere "Enable-UMMailbox: Guida di Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)all'indirizzo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

