---
title: "Lync Server 2013: creare o modificare un oggetto contatto telefonico per l'area comune"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e9e7ddf1a4911b9afb3428531911223f62ea723
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Creare o modificare un oggetto contatto telefonico per l'area comune in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

Per creare oggetti di contatto di servizi di dominio Active Directory per tutti i telefoni dell'area comune, usare il cmdlet **New-CsCommonAreaPhone** . Questo cmdlet può creare nuovi oggetti contatto da usare con i telefoni delle aree comuni oppure può associare oggetti contatto esistenti a un nuovo telefono con area comune. Per modificare le proprietà degli oggetti contatto associati ai telefoni delle aree comuni, usare il cmdlet **Set-CsCommonAreaPhone** . I parametri facoltativi per **Set-CsCommonAreaPhone** consentono di modificare gli elementi, ad esempio il nome visualizzato di Active Directory del contatto o l'URI (Uniform Resource Identifier) line associato al telefono, e di abilitare e disabilitare l'account da usare con Lync Server. Per informazioni dettagliate su tutte le modifiche disponibili, vedere la sezione parametri in [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Per informazioni dettagliate sui parametri **New-CsCommonAreaPhone** , vedere [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

È possibile eseguire questi due cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Creazione di un oggetto contatto telefonico per l'area comune

  - Per creare un nuovo oggetto contatto telefonico per l'area comune, usare il cmdlet **New-CsCommonAreaPhone** . Quando si crea un oggetto contatto, è necessario specificare almeno le informazioni seguenti:
    
      - **LineUri**: il numero di telefono assegnato al telefono per l'area comune. Tenere presente che è necessario usare il formato E. 164 quando si specifica il numero di telefono.
    
      - **RegistrarPool**: il nome di dominio completo (FQDN) del pool di registrar che ospiterà l'oggetto contatto.
    
      - **Ou**: nome distinto del contenitore di Active Directory in cui verrà creato l'oggetto contatto.
    
    Ti consigliamo anche di specificare un nome visualizzato per servizi di dominio Active Directory. In caso contrario, sarà necessario usare un GUID per specificare l'identità del telefono. Ad esempio:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Modifica di un oggetto contatto telefonico per l'area comune

  - Per modificare le proprietà di un telefono di area comune esistente, usare il cmdlet **Set-CsCommonAreaPhone** per l'oggetto contatto. Ad esempio, questo comando configura l'indirizzo SIP per il telefono per l'area comune con la lobby DisplayName:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) e al cmdlet [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

