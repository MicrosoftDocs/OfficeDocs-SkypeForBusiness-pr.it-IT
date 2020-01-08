---
title: 'Lync Server 2013: Configurare dial plan per le conferenze telefoniche con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11424148db609fa8225b6c98d1de52fa360eb044
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Configurare dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-25_

Quando si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario creare o modificare uno o più piani di chiamata per il routing dei numeri di telefono di Access per le chiamate in ingresso. Assicurarsi che almeno una regola di normalizzazione in ogni dial plan converta le estensioni telefoniche in numeri di telefono completi nel formato E. 164. Gli utenti di servizi di conferenza telefonica con accesso esterno partecipano alle conferenze come utenti autenticati dell'organizzazione immettendo il PIN (Personal Identification Number) e il relativo numero di telefono. È necessaria una regola di normalizzazione per convertire le estensioni in numeri di telefono completi in modo che gli utenti possano essere autenticati quando immettono solo un'estensione telefonica.

Per configurare i dial plan per i servizi di conferenza telefonica con accesso esterno, eseguire le operazioni seguenti:

  - Se si distribuisce o meno Enterprise Voice, modificare il dial plan globale per aggiungere un'area di conferenza telefonica con accesso esterno e verificare che una regola di normalizzazione converta accuratamente i numeri di accesso esterno. Per istruzioni dettagliate, vedere [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Se non è stata distribuita VoIP aziendale, creare piani di chiamata per i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso. Assicurati di includere un'area di conferenza telefonica con accesso esterno. Per istruzioni dettagliate, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Se Enterprise Voice è stato distribuito, modificare i piani per le chiamate vocali aziendali in base alle esigenze per includere le aree geografiche e usare le regole di normalizzazione per i numeri di accesso esterno. Per istruzioni dettagliate, vedere [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). È anche possibile creare piani di chiamata dedicati usati solo per i numeri di accesso esterno. Per istruzioni dettagliate, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Per informazioni dettagliate sulla pianificazione delle aree geografiche, vedere Requisiti per i servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Visualizzare le informazioni di dial plan in Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

