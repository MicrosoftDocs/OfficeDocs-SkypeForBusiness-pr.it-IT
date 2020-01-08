---
title: Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6e028afcd3a9affc6c316b7cb373e124e6d5b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server da Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2019-03-22_

Il processo di provisioning per la connettività Lync-Skype è stato modificato rispetto ai metodi di provisioning di PIC precedenti. Questo processo di provisioning può richiedere fino a 30 giorni per il completamento. Prima di completare i passaggi rimanenti di questo documento, è consigliabile iniziare prima questo processo. Dopo aver completato il processo di provisioning Lync-Skype per l'account, l'account viene attivato e gli utenti idonei sono abilitati per la connettività di messaggistica istantanea pubblica.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Per eseguire il provisioning della connettività di Lync-Skype, sono necessarie le informazioni seguenti:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Numero di contratto Microsoft</p></li>
<li><p>Nome di dominio completo (FQDN) di Access Edge Services</p></li>
<li><p>Domini SIP (Session Initiation Protocol)</p></li>
<li><p>Altri FQDN dei servizi di Access Edge aggiuntivi</p></li>
<li><p>Informazioni di contatto</p></li>
</ol></td>
</tr>
</tbody>
</table>

A partire da aprile 2019, si fermerà la raccolta e la conservazione delle informazioni di contatto per i clienti che hanno effettuato il provisioning per la Federazione Skype tramite il sito Web pic.lync.com. Questa modifica viene eseguita per garantire che il sistema di provisioning di pic.lync.com aderisca ai criteri di privacy Microsoft. 

Al termine della modifica, non sarà più possibile inviare aggiornamenti tramite posta elettronica in sospeso. Le modifiche al provisioning di PIC vengono in genere completate entro 24-48 ore dopo l'immissione. Se si verificano ancora problemi con la Federazione di Skype 48 ore dopo l'invio di una richiesta di provisioning, contattare il supporto tecnico Microsoft per approfondire ulteriormente.

> [!IMPORTANT]
> Come parte di questa modifica, tutte le informazioni di contatto inserite in precedenza verranno eliminate dal sistema entro la fine di aprile 2019.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Per avviare il processo di provisioning per Lync-connettività Skype:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Accedi al sito Web <strong>https://pic.lync.com</strong>, usando il tuo Microsoft Windows Live ID.</p></li>
<li><p>Selezionare il tipo di contratto Microsoft Licensing.</p></li>
<li><p>Selezionare la casella di controllo per verificare di aver letto e accettato i diritti di utilizzo del prodotto per Lync Server.</p></li>
<li><p>Nella pagina <strong>Avvia una richiesta di provisioning</strong> fare clic sul collegamento appropriato per avviare una richiesta di provisioning:</p></li>
<li><p>Nella pagina <strong>specifica informazioni di provisioning</strong> immettere l' <strong>FQDN del servizio Edge di Access</strong>. Ad esempio, <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Dopo il 1 ° luglio 2017 Microsoft richiederà inoltre ai clienti che il record SRV DNS federativo distribuito per la connettività di messaggistica istantanea pubblica continui a funzionare.

</li>
<li><p>Immettere almeno uno o più nomi di dominio SIP e quindi fare clic su <strong>Aggiungi</strong>.</p>



> [!IMPORTANT]
> Per completare il processo di provisioning è necessario almeno un server Edge di Access e un dominio SIP. Il dominio SIP e l'Access Edge Server devono essere attivi, funzionanti e raggiungibili in rete.

</li>
<li><p>Nell'elenco dei <strong>provider di servizi di messaggistica istantanea pubblici</strong>selezionare <strong>Skype</strong> e fare clic su <strong>Avanti</strong> per aggiungere le informazioni di contatto e inviare la richiesta di provisioning.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Dopo l'invio della richiesta di provisioning, possono essere necessarie fino a 30 giorni per l'attivazione dell'account e consentire agli utenti di essere abilitati per la connettività di messaggistica istantanea pubblica.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Abilitazione della Federazione e della connettività per messaggistica istantanea pubblica (PIC)

Dopo aver inviato la richiesta di provisioning, è possibile concentrarsi sull'ambiente Lync Server e sulle attività amministrative necessarie per configurare la connettività Lync-Skype. In questa sezione Supponiamo che l'amministratore di Lync Server abbia distribuito Lync Server e abbia configurato l'accesso esterno. Per altre informazioni sulla configurazione dell'accesso esterno per Lync Server, vedere "pianificazione per l'accesso degli utenti [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) esterni" all'indirizzo e "distribuzione di [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)accessi esterni agli utenti".

Per preparare l'ambiente Lync Server per la connettività Lync-Skype, l'amministratore di Lync Server deve completare le tre attività seguenti:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. Configurare la Federazione e PIC

La Federazione è necessaria per consentire agli utenti Skype di comunicare con gli utenti di Lync dell'organizzazione. La connettività di messaggistica istantanea pubblica (PIC) è una classe di Federazione e deve essere configurata per consentire agli utenti di Lync di comunicare con gli utenti Skype. La Federazione e il PIC vengono configurati tramite il pannello di controllo di Lync Server, illustrato di seguito.

<div>


> [!IMPORTANT]
> La Federazione PIC non è più supportata da Live Communication Server 2005 SP1 o da Office Communications Server 2007. Le piattaforme supportate per la Federazione PIC includono Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. Configurare almeno un criterio per supportare l'accesso degli utenti federati

Usando il pannello di controllo di Lync Server, un amministratore deve configurare uno o più criteri di accesso degli utenti esterni per controllare se gli utenti Skype possono collaborare con gli utenti interni di Lync Server.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Configurare l'impostazione del provider di Skype PIC per Lync

Usando Lync Server Management Shell, un amministratore deve configurare i criteri client di Lync per visualizzare Skype come provider di PIC aggiuntivo.

<div>


> [!NOTE]
> Gli utenti dei provider di servizi di messaggistica istantanea pubblica (PIC) non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione finché non si configura almeno un criterio (passaggio 2, in precedenza in questa procedura) per supportare la connettività di messaggistica istantanea pubblica.<BR>Per configurare la Federazione e il PIC, vedere "abilitare o disabilitare la Federazione e la connettività <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>per la messaggistica istantanea pubblica".<BR>Per configurare almeno un criterio per il supporto dell'accesso degli utenti federati, vedere "configurare i criteri per controllare l'accesso <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>degli utenti pubblici".



</div>

1.  Da un server front-end di Lync Server aprire Lync Server Management Shell.

2.  Eseguire i due comandi seguenti:
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Se non si dispone già di un provider PIC nell'ambiente e si crea un nuovo provider PIC, non è necessario eseguire il cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Aggiunta in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, NameDecorationRoutingDomain e NameDecorationExcludedDomainList migliorano la situazione in cui gli utenti di Lync aggiungono contatti Skype necessari per "decorare" i domini non Microsoft per identificarli e instradarli a Skype (il formato di: User (contoso. com) @msn. com). Queste nuove impostazioni consentiranno la formattazione automatica dell'invio dell'utente dell'indirizzo nella finestra di dialogo "Aggiungi contatto Skype" con NameDecorationRoutingDomain (che deve essere impostato su msn.com) se non contiene i domini nel NameDecorationExcludedDomainList ( Attualmente possiamo supportare msn.com, live.com, Hotmail.com, outlook.com).

        
        </div>

3.  Da un client Lync è ora possibile selezionare Skype come provider PIC e aggiungere un client Skype specificando il proprio account Microsoft. Inoltre, un utente Skype che si è Unito e ha effettuato l'accesso con il proprio account Microsoft può inviare una richiesta di contatto agli utenti di Lync. Per altre informazioni sugli account Microsoft, vedere [che cos'è un account Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Per altre informazioni sull'aggiunta di client a Lync, vedere [uso della connettività Lync-Skype in Lync Server 2013 come utente finale](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Per informazioni dettagliate sulla modifica di provider ospitati, vedere la pagina relativa alla creazione o modifica di [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)provider federati SIP ospitati.

In questo articolo vengono completate le attività amministrative che devono essere eseguite nel server. È ora configurato per la connettività Lync-Skype.

</div>

</div>

<div>

## <a name="additional-resources"></a>Risorse aggiuntive

[Uso della connettività Lync-Skype in Lync Server 2013 come utente finale](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Guida al provisioning della connettività Lync-Skype in Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

