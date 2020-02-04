---
title: Verificare che tutti gli oggetti contatto di messaggistica unificata di Exchange vengano rimossi dal pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e49aa2fdef3731a34de05e04b8195cb8aa32cd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Verificare che tutti gli oggetti contatto di messaggistica unificata di Exchange vengano rimossi dal pool legacy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-26_

Puoi usare lo strumento **OCSUmUtil** o il cmdlet **Get-CsExUmContact** per verificare che gli oggetti contatto di messaggistica unificata di Exchange siano stati rimossi dal pool legacy di Office Communications Server 2007 R2. **OCSUmUtil** si trova nella cartella seguente:

\\% Programmi% file\\comuni Lync Server 2013\\supporta\\OcsUmUtil. exe

**OCSUmUtil** deve essere eseguito da un account utente che include:

  - Appartenenza al gruppo RTCUniversalServerAdmins e RTCUniversalUserAdmins (che include i diritti per la lettura delle impostazioni della messaggistica unificata di Exchange Server)

  - Diritti di dominio per creare oggetti contatto nel contenitore dell'unità organizzativa specificata

Per informazioni dettagliate sull'uso del cmdlet **Get-CsExUmContact** , vedere [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) nella documentazione di Lync Server Management Shell.

</div>

<span> </span>

</div>

</div>

</div>

