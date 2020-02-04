---
title: 'Lync Server 2013: Configurazione della federazione di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Configurazione della federazione di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-27_

Se si è già distribuito Edge Server o server, l'aggiunta delle caratteristiche degli scenari federati è semplice. Se non è stato configurato Edge Server, è necessario farlo per primo. Per informazioni dettagliate, vedere [pianificazione per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione di pianificazione e [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> Se si intende configurare una combinazione di federazione XMPP, Federazione Lync o connettività di messaggistica istantanea pubblica, è possibile distribuirle contemporaneamente o una alla volta. Se si configurano le opzioni tramite il generatore di topologia e Lync Server Management Shell, eseguire la distribuzione guidata su Edge Server dopo la configurazione delle opzioni per uno, due o tutti e tre i tipi di federazione, è possibile ridurre il numero di passaggi necessari.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Configurazione della federazione Lync in Generatore di topologie e distribuzione guidata

1.  In un server front-end aprire Generatore di topologia. Espandere pool di bordi e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool Edge Server. Selezionare Modifica proprietà.

2.  In modifica proprietà in generale selezionare Abilita federazione per questo pool di bordi (porta 5061). Fare clic su OK.

3.  Fare clic su azione, selezionare topologia, quindi pubblica. Quando viene richiesto di pubblicare la topologia, fare clic su Avanti. Al termine della pubblicazione, fare clic su fine.

4.  Nell'Edge Server aprire la distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna Lync Server System, quindi fare clic su Imposta o Rimuovi componenti di Lync Server. Fare di nuovo clic su Esegui.

5.  In configurazione componenti di Lync Server fare clic su Avanti. La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite. Dopo aver completato la distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su fine per completare la distribuzione.
    
    <div>
    

    > [!IMPORTANT]  
    > È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la Federazione solo un pool di Edge o un server perimetrale dell'organizzazione. Tutti gli accessi da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passano attraverso lo stesso pool di Edge o un singolo Edge Server. Ad esempio, se la distribuzione include un pool di Edge o un server perimetrale distribuito in New York e uno distribuito a Londra e si Abilita il supporto federativo per il pool Edge di New York o un singolo Edge Server, il traffico di segnale per gli utenti federati passerà attraverso New York Edge pool o Single Edge Server. Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Configurazione della Federazione con i partner

1.  Per configurare una Federazione di successo con un altro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 o Office Communicator 2007, selezionare il tipo di federazione dalla tabella seguente e definire i record SRV DNS, host DNS (A o AAAA per IPv6) e configurare i criteri applicabili al tipo di Federazione:
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Tipo di Federazione</th>
    <th>Record DNS</th>
    <th>Definizione dei criteri</th>
    <th>Note</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Dominio del partner individuato</p></td>
    <td><p>Configurare il record SRV del formato _sipfederationtls. _tcp. &lt;nome&gt;di dominio esterno in cui il valore della porta per il record SRV è TCP 5061 e l' <strong>host che offre questo servizio</strong> è definito come SIP. &lt;Domain Name esterno&gt; : il nome di dominio completo del servizio Access Edge. Per informazioni dettagliate sulla creazione del record SRV, vedere <a href="lync-server-2013-configure-dns-for-edge-support.md">configurare DNS per il supporto Edge in Lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Abilitare o disabilitare l'individuazione dei partner della federazione in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Le versioni precedenti fanno riferimento a questo tipo di federazione come <strong>Federazione avanzata aperta</strong>. La creazione del record SRV è necessaria per questo tipo di Federazione e consente ad altri partner di individuare la Federazione.</p></td>
    </tr>
    <tr class="even">
    <td><p>Dominio partner consentito</p></td>
    <td><p>Configurare il record SRV del formato _sipfederationtls. _tcp. &lt;nome&gt;di dominio esterno in cui il valore della porta per il record SRV è TCP 5061 e l' <strong>host che offre questo servizio</strong> è definito come SIP. &lt;Domain Name esterno&gt; : il nome di dominio completo del servizio Access Edge. Per informazioni dettagliate sulla creazione del record SRV, vedere <a href="lync-server-2013-configure-dns-for-edge-support.md">configurare DNS per il supporto Edge in Lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Le versioni precedenti fanno riferimento a questo tipo di federazione come <strong>Federazione avanzata</strong>. La creazione del record SRV è facoltativa per questo tipo di Federazione e consente ad altri partner di individuare la Federazione. Naturalmente, si tratta di una <strong>Federazione avanzata aperta</strong>o di un <strong>dominio partner individuato</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Server partner consentiti</p></td>
    <td><p>Configurare il nome di dominio SIP e l'FQDN di partner Edge Server come partner federativo nei criteri</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurare il supporto per i domini esterni consentiti in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurare il supporto per i domini esterni bloccati in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Questo tipo di federazione è la definizione di una relazione uno-a-uno e non consente l'individuazione di altri partner federativi. Ogni partner federativo è configurato in modo esplicito. Nelle versioni precedenti questa operazione era denominata <strong>Federazione diretta</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>Provider di hosting e provider di messaggistica istantanea pubblica</p></td>
    <td><p>Non sono definiti requisiti DNS specifici per questo tipo di Federazione</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Creare o modificare provider federati SIP pubblici in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creare o modificare provider federati SIP ospitati in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Questo tipo di Federazione definisce i servizi e i provider di hosting che si desidera configurare per gli utenti. Gli usi tipici includono la configurazione per i provider di messaggistica istantanea pubblici come Windows Live Messenger, Yahoo! e AOL, oltre a provider di hosting, ad esempio Lync Online e Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
    > <LI>
    > <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
    > <LI>
    > <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Definire e configurare l'host DNS obbligatorio (A o AAAA per IPv6) e i record SRV DNS

3.  Definire e configurare i criteri usando il pannello di controllo di Lync Server o usando Lync Server Management Shell e i cmdlet appropriati. Per informazioni dettagliate sui cmdlet di Lync Server Management Shell, vedere [cmdlet federativo e Access esterni in Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync room System (LRS) non Mostra il pulsante partecipa per le riunioni inviate dagli organizzatori in partner Lync federati. Per visualizzare un collegamento a una riunione di join in LRS, l'organizzazione di invio deve abilitare il formato TNEF usando il cmdlet seguente:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Tieni presente che questo non è LRS specifico. Anche Outlook e Lync non visualizzano collegamenti di join in questo caso, poiché le proprietà MAPI non vengono trasportate, ma nel caso di Outlook l'utente può aprire l'invito alla riunione e fare clic sull'URL della riunione. Quando TNEFEnabled è impostato su true Exchange 2013 non esegue il striping delle proprietà MAPI incluso OnlineMeetingExternalLink e il pulsante partecipa verrà visualizzato nel promemoria.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Gestione della federazione e dell'accesso esterno a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

