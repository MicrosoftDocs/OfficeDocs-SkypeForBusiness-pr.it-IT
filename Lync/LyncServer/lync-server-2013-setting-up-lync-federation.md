---
title: 'Lync Server 2013: configurazione della Federazione di Lync'
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
ms.openlocfilehash: cea596f571064a3b72ecbb3b0c2b56c2179aa315
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Configurazione della Federazione di Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-27_

Se il server o i server perimetrali sono già stati distribuiti, l'aggiunta delle funzionalità degli scenari federati è un'operazione semplice. Se i server perimetrali non sono stati impostati, è necessario prima eseguire questa operazione. Per informazioni dettagliate, vedere: [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione e [distribuzione di accesso utente esterno in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> Se si intende configurare una combinazione di federazione XMPP, Lync o connettività di messaggistica istantanea, è possibile effettuare la distribuzione contemporaneamente o un componente alla volta. Se si configurano le opzioni attraverso il Generatore di topologie e Lync Server Management Shell, eseguire la Distribuzione guidata nel server perimetrale dopo avere configurato le opzioni per uno, due o tutti e tre i tipi di federazione. In questo modo si ridurrà il numero di passaggi necessari.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Configurazione della federazione Lync nel Generatore di topologie e nella Distribuzione guidata

1.  In un server Front End aprire il Generatore di topologie. Espandere Pool di server perimetrali e quindi fare clic con il pulsante destro del mouse sul server perimetrale o sul pool di server perimetrali. Scegliere Modifica proprietà.

2.  In Modifica Proprietà, sotto Generale, selezionare Abilita federazione per pool di server perimetrali (porta 5061). Fare clic su OK.

3.  Fare clic su Azione, selezionare Topologia, selezionare Pubblica. Quando viene richiesto di pubblicare la topologia, fare clic su Avanti. Quando la pubblicazione è terminata, fare clic su Fine.

4.  Nel server perimetrale, aprire la Distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna il sistema Lync Server, quindi fare clic su Installazione o rimozione componenti di Lync Server.

5.  In Installazione componenti di Lync Server fare clic su Avanti. Nella schermata di riepilogo verranno visualizzate le azioni in esecuzione. Al termine della distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su Fine per completare la distribuzione.
    
    <div>
    

    > [!IMPORTANT]  
    > È possibile selezionare questa opzione, tuttavia solo un pool di server perimetrali o un server perimetrale dell'organizzazione può essere pubblicato esternamente per la federazione. Tutto l'accesso da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passa per lo stesso pool di server perimetrali o server perimetrale singolo. Se, ad esempio, la distribuzione include un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto per la federazione nel pool di server perimetrali o nel server perimetrale di New York, il traffico dei segnali per gli utenti federati passerà per il pool di server perimetrali o il singolo server perimetrale di New York. Ciò vale anche per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiami un utente federato di Londra utilizzerà il pool o il server perimetrale di Londra per il traffico audio/video.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Configurazione della federazione con i partner

1.  Per configurare correttamente una federazione con un altro Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 o Office Communicator 2007, selezionare il tipo di federazione dalla tabella seguente e definire i record DNS SRV, host DNS (A o AAAA per IPv6) e configurare i criteri applicabili al tipo di Federazione:
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Tipo di federazione</th>
    <th>Record DNS</th>
    <th>Definizione criterio</th>
    <th>Notes</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Dominio partner individuato</p></td>
    <td><p>Configurare il record SRV del formato _sipfederationtls. _tcp. &lt;nome&gt;di dominio esterno in cui il valore della porta per il record SRV è TCP 5061 e l' <strong>host che offre questo servizio</strong> è definito come SIP. &lt;nome&gt; di dominio esterno – FQDN del servizio Access Edge. Per informazioni dettagliate sulla creazione del record SRV, vedere <a href="lync-server-2013-configure-dns-for-edge-support.md">configurare DNS per il supporto di Edge in Lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Nelle versioni precedenti si fa riferimento a questo tipo di federazione come alla <strong>Federazione avanzata aperta</strong>. Questo tipo di federazione richiede la creazione del record SRV e ha lo scopo di consentire agli altri partner di individuare la federazione.</p></td>
    </tr>
    <tr class="even">
    <td><p>Dominio partner consentito</p></td>
    <td><p>Configurare il record SRV del formato _sipfederationtls. _tcp. &lt;nome&gt;di dominio esterno in cui il valore della porta per il record SRV è TCP 5061 e l' <strong>host che offre questo servizio</strong> è definito come SIP. &lt;nome&gt; di dominio esterno – FQDN del servizio Access Edge. Per informazioni dettagliate sulla creazione del record SRV, vedere <a href="lync-server-2013-configure-dns-for-edge-support.md">configurare DNS per il supporto di Edge in Lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Le versioni precedenti fanno riferimento a questo tipo di federazione come <strong>Federazione avanzata</strong>. Per questo tipo di federazione la creazione del record SRV è facoltativa e ha lo scopo di consentire agli altri partner di individuare la federazione. Si tratta pertanto di un tipo <strong>Federazione avanzata aperta</strong> o <strong>Dominio partner individuato</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Server partner consentito</p></td>
    <td><p>Configurare il nome di dominio SIP e l'FQDN del server perimetrale partner come partner federativo nei criteri</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configurare il supporto per i domini esterni consentiti in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configurare il supporto per i domini esterni bloccati in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Questo tipo di federazione è la definizione di una relazione uno a uno e non consente l'individuazione di altri partner della federazione. Ogni partner della federazione viene configurato esplicitamente. Nelle versioni precedenti questa funzionalità è denominata <strong>Federazione diretta</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>Provider di hosting e Provider di servizi di messaggistica istantanea pubblici</p></td>
    <td><p>Per questo tipo di federazione non sono definiti requisiti DNS specifici</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Creare o modificare provider federati SIP pubblici in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creare o modificare provider federati SIP ospitati Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Questo tipo di federazione definisce servizi e provider di hosting che si desidera configurare per gli utenti. Tra gli usi più comuni è inclusa la configurazione per i provider di servizi di messaggistica istantanea pubblici come Windows Live Messenger, Yahoo! e AOL, oltre a provider di hosting come Lync Online e Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
    > <LI>
    > <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
    > <LI>
    > <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Definire e configurare qualsiasi host DNS richiesto (A o AAAA per IPv6) e record DNS SRV

3.  Definire e configurare i criteri utilizzando il pannello di controllo di Lync Server o utilizzando Lync Server Management Shell e i cmdlet corretti. Per informazioni dettagliate sui cmdlet di Lync Server Management Shell, vedere [cmdlet per la Federazione e l'accesso esterno in Lync server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync room System (LRS) non Mostra il pulsante Join per le riunioni inviate dagli organizzatori nei partner di Lync federati. Affinché un collegamento di partecipazione alle riunioni venga visualizzato in LRS, l'organizzazione di invio deve abilitare TNEF utilizzando il cmdlet seguente:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Si noti che non è specifico di LRS. Anche Outlook e Lync non visualizzano i collegamenti di join in questo caso, poiché le proprietà MAPI non vengono trasportate, ma nel caso di Outlook, l'utente può aprire l'invito alla riunione e fare clic sull'URL della riunione. Quando TNEFEnabled è impostato su true Exchange 2013 non rimuove le proprietà MAPI incluso OnlineMeetingExternalLink e il pulsante join verrà visualizzato nel promemoria.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Gestione della Federazione e dell'accesso esterno a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

