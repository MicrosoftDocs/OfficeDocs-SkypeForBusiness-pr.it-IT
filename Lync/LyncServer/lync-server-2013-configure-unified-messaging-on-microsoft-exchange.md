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
ms.openlocfilehash: d05939f9d15f992d350a6bb756fe3c6b9839c37b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a>Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

In questo argomento viene descritto come configurare la messaggistica unificata di Exchange in un server di Microsoft Exchange per l'utilizzo con VoIP aziendale.

<div>


> [!NOTE]  
> Negli esempi di cmdlet riportati in questo argomento viene fornita la sintassi per la versione di Exchange 2007 di Exchange Management Shell. Se si esegue Exchange 2010 o Exchange 2013, vedere la documentazione appropriata come riferimento.



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a>Per configurare un server che esegue la messaggistica unificata di Exchange Server

1.  Creare un dial plan URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) di messaggistica unificata per ognuno dei profili delle posizioni di VoIP aziendale. Se si sceglie di utilizzare Exchange Management Console, creare un nuovo dial plan con l'impostazione di sicurezza **protetta (scelta preferita)**.
    
    <div>
    

    > [!WARNING]  
    > Se si imposta il valore dell'impostazione di sicurezza su <STRONG>SIP Secured</STRONG> per richiedere la crittografia solo per il traffico SIP, come indicato in precedenza, si noti che questa impostazione di sicurezza su un dial plan non è sufficiente se il pool Front End è configurato per richiedere la crittografia, il che significa che il pool richiede la crittografia per il traffico SIP e RTP. Quando le impostazioni di protezione del dial plan e del pool non sono compatibili, tutte le chiamate alla messaggistica unificata di Exchange dal pool Front End avranno esito negativo, causando un errore che indica che si dispone di un'impostazione di sicurezza incompatibile.

    
    </div>
    
    Se si utilizza Exchange Management Shell, digitare quanto segue:
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    Per dettagli, vedere:
    
      - Per Office Communications Server 2007, vedere "come creare un dial plan URI SIP di messaggistica unificata" [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) e "New-UMDialplan: Exchange 2007 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).
    
      - Per Exchange 2010, vedere "creare un dial plan di messaggistica unificata" [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) e "New-UMDialplan: Exchange 2010 Help [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680)" all'indirizzo.
    
      - Per Exchange 2013, vedere la sezione "messaggistica unificata [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579)" all'indirizzo.
    
    <div>
    

    > [!NOTE]  
    > Se si seleziona un livello di sicurezza di <STRONG>SIPSecured</STRONG> o <STRONG>protetto</STRONG> a seconda che il protocollo SRTP (Secure Real-Time Transport Protocol) venga attivato o disattivato per la crittografia multimediale. Per l'integrazione di Lync Server 2010 con la messaggistica unificata di Exchange, questo dovrebbe corrispondere al livello di crittografia nella configurazione multimediale di Lync Server. La configurazione multimediale di Lync Server può essere visualizzata eseguendo il cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> . Per informazioni dettagliate, vedere Get-CsMediaConfiguration nella documentazione di Lync Server Management Shell.<BR>Per informazioni dettagliate sulla selezione delle impostazioni di protezione VoIP appropriate, vedere <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo di distribuzione per l'integrazione della messaggistica unificata locale e Lync Server 2013</A>.

    
    </div>

2.  Eseguire il cmdlet seguente per ottenere il nome di dominio completo (FQDN) per ogni dial plan di messaggistica unificata:
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    Per dettagli, vedere:
    
      - Per Exchange 2007, vedere "Get-UMDialplan: Exchange 2007 Help" all' [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678)indirizzo.
    
      - Per Exchange 2010, vedere "Get-UMDialplan: Exchange 2010 Help" all' [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679)indirizzo.
    
      - Per Exchange 2013, vedere la sezione "messaggistica unificata [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579)" all'indirizzo.

3.  Registrare il nome del dial plan di ogni dial plan di messaggistica unificata. A seconda della versione di Exchange Server, potrebbe essere necessario utilizzare il nome di dominio completo (FQDN) di tutti i nomi dei dial plan in un secondo momento come nome del dial plan di Lync Server corrispondente di ogni dial plan di messaggistica unificata in modo che corrisponda ai nomi del dial plan.
    
    <div>
    

    > [!NOTE]  
    > I nomi dei dial plan di Lync Server devono corrispondere ai nomi dei dial plan di messaggistica unificata solo se il dial plan di messaggistica unificata è in esecuzione su una versione di Exchange <EM>precedente</EM> a Exchange 2010 SP1.

    
    </div>

4.  Aggiungere il dial plan al server che esegue la messaggistica unificata di Exchange come indicato di seguito:
    
      - Se si sceglie di utilizzare Exchange Management Console, è possibile aggiungere il dial plan dalla finestra delle proprietà del server. Per istruzioni specifiche, vedere la documentazione del prodotto Exchange Server.
        
        Per Exchange 2007, vedere "come aggiungere il server Messaggistica unificata a un dial plan" all' [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681)indirizzo.
        
        Per Exchange 2010, vedere "visualizzazione o configurazione delle proprietà di un server di messaggistica unificata" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).
        
        Per Exchange 2013, vedere la sezione "messaggistica unificata [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579)" all'indirizzo.
    
      - Se si utilizza Exchange Management Shell, eseguire le operazioni seguenti per ognuno dei server di messaggistica unificata di Exchange:
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > Prima di eseguire il passaggio seguente, verificare che tutti gli utenti di VoIP aziendale siano stati configurati con una cassetta postale di Exchange Server.<BR>Per Exchange 2007, vedere la libreria TechNet di Exchange Server 2007 <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>all'indirizzo.<BR>Per Exchange 2010, vedere la libreria TechNet di Exchange Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>all'indirizzo.<BR>Quando si specifica un criterio cassetta postale per ogni dial plan creato nel passaggio 1, selezionare il criterio predefinito o quello creato.

    
    </div>

5.  Passare a \<script di directory\>\\di installazione di Exchange, quindi se Exchange è distribuito in una singola foresta, digitare quanto segue:
    ```console
    exchucutil.ps1
    ```
    In alternativa, se Exchange è distribuito in più foreste, digitare quanto indicato di seguito:
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    dove la foresta FQDN Specifica la foresta in cui è distribuito Lync Server.
    
    Se si dispone di uno o più dial plan di messaggistica unificata associati a più gateway IP, continuare con il passaggio 6. Se i dial plan sono associati a un solo gateway IP, saltare il passaggio 6.
    
    <div>
    

    > [!IMPORTANT]  
    > Riavviare il servizio <STRONG>Lync Server Front End</STRONG> (rtcsrv.exe) <EM>dopo</EM> aver eseguito exchucutil.ps1. In caso contrario, Lync Server non rileverà la messaggistica unificata nella topologia.

    
    </div>

6.  Se si utilizza Exchange Management Shell o Exchange Management Console, disabilitare le chiamate in uscita per tutti i gateway IP associati a ognuno dei dial plan.
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio è necessario per garantire che le chiamate in uscita dal server che esegue la messaggistica unificata di Exchange Server a utenti esterni (ad esempio, come nel caso di scenari di riproduzione su telefono) attraversino in modo affidabile il firewall aziendale.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Quando si seleziona il gateway IP di messaggistica unificata per consentire le chiamate in uscita, scegliere quello che probabilmente gestirà la maggior parte del traffico. Non consentire il traffico in uscita attraverso un gateway IP che si connette a un pool di Director di Lync Server. Evitare anche i pool in un altro sito centrale o in un sito di succursale. È possibile utilizzare uno dei metodi seguenti per bloccare le chiamate in uscita passando da un gateway IP:

    
    </div>
    
      - Se si utilizza Exchange Management Shell, disabilitare ogni gateway IP eseguendo il comando riportato di seguito:
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        Per Exchange 2007, vedere "Set-UMIPGateway: Exchange 2007 Help" all' [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687)indirizzo.
        
        Per Exchange 2010, vedere "Set-UMIPGateway: Exchange 2010 Help" all' [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688)indirizzo.
    
      - Se si utilizza Exchange Management Console, deselezionare la casella di controllo **Consenti chiamate in uscita tramite questo gateway IP** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se il dial plan di messaggistica unificata URI SIP è associato a un solo gateway IP, non impedire le chiamate in uscita tramite il gateway.

    
    </div>

7.  Creare un operatore automatico di messaggistica unificata per ogni dial plan di Lync Server.
    
    <div>
    

    > [!IMPORTANT]  
    > Non includere spazi nel nome dell'operatore automatico.

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    Per dettagli, vedere:
    
      - Per Exchange 2007, vedere "New-UMAutoAttendant: Exchange 2007 Help" all' [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689)indirizzo.
    
      - Per Exchange 2010, vedere "New-UMAutoAttendant: Exchange 2010 Help" all' [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690)indirizzo.
    
    Il passaggio seguente deve essere eseguito per ogni utente dopo aver abilitato gli utenti di Lync Server per VoIP aziendale e conoscere gli URI SIP.

8.  Associare gli utenti di messaggistica unificata di Exchange (ognuno dei quali deve essere configurato con una cassetta postale di Exchange) al dial plan di messaggistica unificata e creare un URI SIP per ogni utente.
    
    <div>
    

    > [!NOTE]  
    > L' <STRONG>parametro SIPResourceIdentifier</STRONG> nell'esempio seguente deve essere l'indirizzo SIP dell'utente di Lync Server.

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    Per dettagli, vedere:
    
      - Per Exchange 2007, vedere "Enable-UMMailbox: Exchange 2007 Help" all' [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691)indirizzo.
    
      - Per Exchange 2010, vedere "Enable-UMMailbox: Exchange 2010 Help" all' [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692)indirizzo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

