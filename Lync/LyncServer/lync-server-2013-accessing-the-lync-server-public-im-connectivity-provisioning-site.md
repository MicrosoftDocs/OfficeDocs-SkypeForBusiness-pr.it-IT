---
title: Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44692fd6267e23c98ecef1ca227cbde5289a44b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server da Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2019-03-22_

Il processo di provisioning per la connettività Lync-Skype è stato modificato rispetto ai metodi di provisioning PIC precedenti. Questo processo di provisioning può richiedere fino a 30 giorni per il completamento. Si consiglia di iniziare il processo prima di completare i passaggi rimanenti del documento. Dopo aver completato il processo di provisioning di Lync-Skype per l'account, l'account è stato attivato e gli utenti idonei sono abilitati per la connettività per la messaggistica istantanea pubblica.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Per eseguire il provisioning della connettività Lync-Skype, sono necessarie le seguenti informazioni:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Numero del contratto Microsoft</p></li>
<li><p>Nome di dominio completo (FQDN) del servizio Access Edge</p></li>
<li><p>Domini SIP (Session Initiation Protocol)</p></li>
<li><p>Qualsiasi FQDN del servizio Access Edge aggiuntivo</p></li>
<li><p>Informazioni di contatto</p></li>
</ol></td>
</tr>
</tbody>
</table>

A partire da aprile 2019, si interromperà la raccolta e la conservazione delle informazioni di contatto per i clienti che sono stati provisionati per la Federazione Skype tramite il sito Web pic.lync.com. Questa modifica viene apportata per garantire che il sistema di provisioning di pic.lync.com sia conforme ai criteri di privacy di Microsoft. 

Una volta che questa modifica è attiva, non sarà più possibile fornire gli aggiornamenti della posta elettronica sulle modifiche di provisioning in sospeso. Le modifiche del provisioning delle PIC vengono in genere completate entro 24-48 ore dopo l'immissione. Se si verificano ancora problemi relativi alla Federazione di Skype 48 ore dopo l'invio di una richiesta di provisioning, contattare il supporto tecnico Microsoft per approfondire ulteriormente.

> [!IMPORTANT]
> Come parte di questa modifica, tutte le informazioni di contatto inserite in precedenza verranno eliminate dal sistema entro la fine di aprile 2019.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Per avviare il processo di provisioning per la connettività Lync-Skype:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Accedere al sito Web <strong>https://pic.lync.com</strong>utilizzando il Microsoft Windows Live ID.</p></li>
<li><p>Selezionare il tipo di contratto Microsoft Licensing.</p></li>
<li><p>Selezionare la casella di controllo per verificare che i diritti di utilizzo del prodotto siano stati letti e accettati per Lync Server.</p></li>
<li><p>Nella pagina <strong>Avvia una richiesta di provisioning</strong> fare clic sul collegamento appropriato per avviare una richiesta di provisioning:</p></li>
<li><p>Nella pagina <strong>specifica informazioni di provisioning</strong> immettere il <strong>nome di dominio completo del servizio Access Edge</strong>. Ad esempio, <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Dopo il 1 ° luglio 2017 Microsoft richiederà inoltre ai clienti che il record DNS di Federazione SRV è stato distribuito per la connettività di messaggistica istantanea pubblica per continuare a funzionare.

</li>
<li><p>Immettere almeno uno o più nomi di dominio SIP e quindi fare clic su <strong>Aggiungi</strong>.</p>



> [!IMPORTANT]
> Per completare il processo di provisioning, sono necessari almeno un server perimetrale di accesso e un dominio SIP. Il dominio SIP e il server perimetrale di accesso devono essere attivi, funzionanti e raggiungibili sulla rete.

</li>
<li><p>Nell'elenco dei <strong>provider di servizi di messaggistica istantanea pubblica</strong>, selezionare <strong>Skype</strong> e fare clic su <strong>Avanti</strong> per aggiungere le informazioni di contatto e inviare la richiesta di provisioning.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Dopo aver inoltrato la richiesta di provisioning, possono essere necessari fino a 30 giorni affinché l'account venga attivato e gli utenti siano abilitati per la connettività per la messaggistica istantanea pubblica.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Abilitazione della Federazione e della connettività per la messaggistica istantanea pubblica (PIC)

Dopo aver inoltrato la richiesta di provisioning, è possibile concentrarsi sull'ambiente Lync Server e sulle attività amministrative necessarie per configurare la connettività Lync-Skype. In questa sezione si presuppone che l'amministratore di Lync Server abbia distribuito Lync Server e abbia configurato l'accesso esterno. Per ulteriori informazioni sulla configurazione dell'accesso esterno per Lync Server, vedere la sezione relativa alla pianificazione dell'accesso [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) degli utenti esterni in e "Deploying [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)External User Access" all'indirizzo.

Per preparare l'ambiente Lync Server per la connettività Lync-Skype, è necessario che l'amministratore di Lync Server completi le tre attività seguenti:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Configurazione della Federazione e del PIC

La Federazione è necessaria per consentire agli utenti di Skype di comunicare con gli utenti di Lync nell'organizzazione. La connettività per la messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Lync di comunicare con gli utenti di Skype. La Federazione e il PIC sono configurati utilizzando il pannello di controllo di Lync Server, mostrato di seguito.

<div>


> [!IMPORTANT]
> La Federazione PIC non è più supportata da Live Communication Server 2005 SP1 o da Office Communications Server 2007. Le piattaforme supportate per la Federazione PIC sono Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Configurare almeno un criterio per il supporto dell'accesso utente federato

Se si utilizza il pannello di controllo di Lync Server, un amministratore deve configurare uno o più criteri di accesso utente esterno per controllare se gli utenti di Skype possono collaborare con gli utenti interni di Lync Server.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Configurare l'impostazione di Skype PIC provider per Lync

Utilizzando Lync Server Management Shell, un amministratore deve configurare il criterio client di Lync per visualizzare Skype come un ulteriore provider PIC.

<div>


> [!NOTE]
> Gli utenti dei provider di servizi di connettività di messaggistica istantanea pubblica non possono partecipare a conferenze o messaggistica istantanea nell'organizzazione fino a quando non si configura anche almeno un criterio (passaggio 2, più indietro in questa procedura) per supportare la connettività per la messaggistica istantanea pubblica.<BR>Per configurare la Federazione e il PIC, vedere "abilitare o disabilitare la Federazione e la connettività <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>per la messaggistica istantanea pubblica" all'indirizzo.<BR>Per configurare almeno un criterio per il supporto dell'accesso degli utenti federati, vedere la sezione relativa alla configurazione di criteri per <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>il controllo dell'accesso degli utenti pubblici all'indirizzo.



</div>

1.  Da un server front-end di Lync Server, aprire Lync Server Management Shell.

2.  Eseguire i due comandi seguenti:
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Se non si dispone già di un provider PIC nel proprio ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificare e instradarli a Skype (il formato di: User (contoso. com) @msn. com). Queste nuove impostazioni consentiranno la formattazione automatica della finestra di dialogo "Aggiungi contatto Skype" con il NameDecorationRoutingDomain (che dovrebbe essere impostato su msn.com) se non contiene i domini in NameDecorationExcludedDomainList ( Attualmente è in grado di supportare msn.com, live.com, Hotmail.com, outlook.com).

        
        </div>

3.  Da un client Lync, è ora possibile selezionare Skype come provider PIC e aggiungere un client Skype specificando il proprio account Microsoft. Inoltre, un utente Skype che ha eseguito l'Unione e l'accesso con il proprio account Microsoft può inviare una richiesta di contatto agli utenti di Lync. Per ulteriori informazioni sugli account Microsoft, vedere [che cos'è un account Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Per ulteriori informazioni sull'aggiunta di client a Lync, vedere [utilizzo della connettività Lync-Skype in Lync Server 2013 come utente finale](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Per informazioni dettagliate sulla modifica dei provider ospitati, vedere "creare o modificare provider federati SIP ospitati" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065).

Vengono completate le attività amministrative che devono essere eseguite sul server. È ora configurato per la connettività Lync-Skype.

</div>

</div>

<div>

## <a name="additional-resources"></a>Risorse aggiuntive

[Utilizzo della connettività Lync-Skype in Lync Server 2013 come utente finale](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Guida al provisioning della connettività Lync-Skype in Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

