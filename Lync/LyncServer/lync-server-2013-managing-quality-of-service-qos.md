---
title: 'Lync Server 2013: gestire la qualità del servizio (QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Gestione della qualità del servizio (QoS) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

La qualità del servizio (QoS) è una tecnologia di rete usata in alcune organizzazioni per offrire un'esperienza ottimale per l'utente finale per le comunicazioni audio e video. Il QoS viene usato più comunemente nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete che competono per una quantità relativamente piccola di larghezza di banda disponibile, la qualità del servizio consente agli amministratori di assegnare priorità più alte ai pacchetti trasporto di dati audio o video. Assegnando a questi pacchetti una priorità più alta, le comunicazioni audio e video possono essere completate più rapidamente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni come i trasferimenti di file, la navigazione web o i backup di database. Il motivo è che i pacchetti di rete usati per i trasferimenti di file o i backup di database hanno la priorità "migliore sforzo".

<div>


> [!NOTE]  
> Come regola generale, la qualità del servizio si applica solo alle sessioni di comunicazione nella rete interna. Quando si implementa QoS, si configurano i server e i router per supportare il contrassegno dei pacchetti. Tuttavia, configuri questi dispositivi per supportare il contrassegno dei pacchetti in modo particolare. Non si può presupporre che la qualità del servizio sarà supportata su Internet o su altre reti. Anche se la qualità se il servizio è supportato in altre reti, non c'è alcuna garanzia che la QoS venga configurata allo stesso modo in cui il servizio è stato configurato nella rete.



</div>

Microsoft Lync Server 2013 non richiede la qualità del servizio; Se attualmente non si usa QoS, non è necessario installare il servizio prima di installare Lync Server 2013. Se si verifica una notevole quantità di perdita di pacchetti nella rete, il metodo consigliato per alleviare questo problema consiste nell'aggiungere ulteriore larghezza di banda. Se non è possibile aggiungere più larghezza di banda, è consigliabile implementare invece la qualità del servizio.

Lync Server 2013 offre il supporto completo per la qualità del servizio: ciò significa che le organizzazioni che già usano QoS possono integrare facilmente Lync Server nell'infrastruttura di rete esistente. A tale scopo, è necessario eseguire le attività seguenti:

  - [Abilitazione del QoS in Lync Server 2013 per i dispositivi che non sono basati su Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Per impostazione predefinita, QoS è disabilitato per i computer e altri dispositivi (ad esempio iPhone) che eseguono altri sistemi operativi. Anche se è possibile usare Lync Server per abilitare e disabilitare la qualità del servizio per i dispositivi, in genere non è possibile usare il prodotto per modificare i codici DSCP usati da questi dispositivi.

  - [Configurazione di intervalli di porte in Lync server 2013 per i servizi di conferenza, applicazione e Mediation Server](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). È necessario prenotare un set di porte univoco per tipi di pacchetto diversi, ad esempio audio e video. Con Lync Server 2013 non è possibile abilitare o disabilitare la qualità del servizio, ad esempio impostando un valore di proprietà su true o su false. Puoi invece abilitare la qualità del servizio configurando gli intervalli di porte e quindi creando e applicando criteri di gruppo. Se in seguito si decide di non usare QoS, è possibile "disabilitare" la qualità del servizio semplicemente rimuovendo gli oggetti Criteri di gruppo appropriati.

  - [Configurazione degli intervalli di porte per gli Edge Server in Lync server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Anche se non è necessario, è possibile configurare gli Edge Server in modo da usare gli stessi intervalli di porte degli altri server.

  - [Configurazione degli intervalli di porte per i client Microsoft Lync in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Questi intervalli di porte si applicano solo ai computer client e in genere non corrispondono agli intervalli di porte configurati nei server.

  - [Configurazione di un criterio di qualità dei servizi in Lync server 2013 per le conferenze, le applicazioni e i server di mediazione](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Questi criteri determinano i codici DSCP applicati a tipi di pacchetto diversi.

  - [Configurazione di un criterio di qualità dei servizi per i server a/V Edge in Lync server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Questa operazione deve essere eseguita solo per il lato interno degli Edge Server. Questo perché la qualità del servizio è progettata per l'uso nella rete interna e non in Internet.

  - [Configurare i criteri di qualità dei servizi in Lync Server 2013 per i client in uso in Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Tieni presente che Microsoft Lync Server 2013 non supporta QoS per altri sistemi operativi Windows, come Windows Vista o Windows XP.

  - [Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). Per impostazione predefinita, QoS è abilitato per i dispositivi Lync Phone Edition. Tuttavia, potresti voler cambiare il valore di DSCP predefinito per assicurarti che tutti i pacchetti audio dell'organizzazione usino lo stesso codice DSCP.

<div>


> [!NOTE]  
> Se si usa Microsoft Windows Server 2012 o Windows Server 2012 R2, potrebbe essere interessante il nuovo set di cmdlet di Windows PowerShell disponibili per la gestione della qualità del servizio su tale piattaforma. Per altre informazioni, vedere cmdlet per la qualità della rete di servizi in Windows [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)PowerShell at.



</div>

</div>

<span> </span>

</div>

</div>

</div>

