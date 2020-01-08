---
title: Importare criteri e impostazioni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4a4d86d687236934c319e3fb7bd5e6c8027a73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>Importare criteri e impostazioni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Dopo aver merge le informazioni sulla topologia di Office Communications Server 2007 R2 con il pool di piloti di Lync Server 2013, è necessario eseguire un cmdlet Lync Server 2013 Management Shell per eseguire la migrazione dei criteri e delle impostazioni di configurazione di Office Communications Server 2007 R2 al pool di piloti di Lync Server 2013.

Il cmdlet **Import-CsLegacyConfiguration** importa i criteri, le route vocali, i dial plan, gli URL di Communicator Web Access e i numeri di accesso per le chiamate in ingresso in Lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Per eseguire la migrazione di criteri e impostazioni

1.  Nel server front-end di Lync Server 2013 Avviare Lync Server Management Shell.

2.  Nella riga di comando digitare quanto segue:
    
        Import-CsLegacyConfiguration
    
    Dopo aver importato i criteri, usare la procedura seguente per visualizzare i criteri importati nel pannello di controllo di Lync Server.

</div>

<div>

## <a name="to-view-imported-policies"></a>Per visualizzare i criteri importati

1.  Aprire il pannello di controllo di Lync Server 2013.

2.  Fare clic su **routing vocale** e visualizzare i criteri importati.

3.  Fare clic su servizi di **conferenza** e visualizzare i criteri importati.

4.  Fare clic su **Federazione e accesso esterno** e visualizzare i criteri importati.

5.  Fare clic su **monitoraggio e archiviazione** e visualizzare i criteri importati.

</div>

</div>

<span> </span>

</div>

</div>

</div>

