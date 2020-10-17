---
title: 'Lync Server 2013: configurare dial plan per le conferenze telefoniche con accesso esterno'
description: 'Lync Server 2013: configurare i dial plan per le conferenze telefoniche con accesso esterno.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28123f905288ce35b6f470168962a3d8e6faa22b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567582"
---
# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Configurare i dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-25_

Quando si distribuiscono le conferenze telefoniche con accesso esterno, è necessario creare o modificare uno o più dial plan per il routing dei numeri di telefono di accessi. Assicurarsi che almeno una regola di normalizzazione in ogni dial plan converta le estensioni telefoniche in numeri di telefono completi nel formato E. 164. Gli utenti delle conferenze telefoniche con accesso esterno partecipano alle conferenze come utenti autenticati dell'organizzazione immettendo il proprio PIN (Personal Identification Number) e il relativo numero di telefono. È necessaria una regola di normalizzazione per convertire le estensioni in numeri di telefono completi in modo che gli utenti possano essere autenticati quando immettono solo un interno telefonico.

Per impostare i dial plan per le conferenze telefoniche con accesso esterno, eseguire le operazioni seguenti:

  - Se si distribuisce o meno VoIP aziendale, modificare il dial plan globale per aggiungere un'area di conferenza telefonica con accesso esterno e per assicurarsi che una regola di normalizzazione converta con precisione i numeri di accesso telefonico in ingresso. Per istruzioni dettagliate, vedere [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Se non è stata distribuita VoIP aziendale, creare i dial plan per i numeri di accesso per le conferenze telefoniche con chiamata in ingresso. Assicurarsi di includere un'area di conferenza telefonica con accesso esterno. Per istruzioni dettagliate, vedere [creazione di un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Se è stata distribuita VoIP aziendale, modificare i piani di chiamata VoIP aziendale in base alle esigenze per includere le aree geografiche e utilizzare le regole di normalizzazione appropriate per i numeri di accesso esterno. Per istruzioni dettagliate, vedere [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). È inoltre possibile creare piani di chiamata dedicati che vengono utilizzati solo per i numeri di accesso esterno. Per istruzioni dettagliate, vedere [creazione di un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Per informazioni dettagliate sulla pianificazione delle aree geografiche, vedere Servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Visualizzare le informazioni sul dial plan in Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

