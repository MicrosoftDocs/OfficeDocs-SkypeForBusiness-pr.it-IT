---
title: 'Lync Server 2013: creare o modificare un oggetto contatto telefonico di area comune'
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
ms.openlocfilehash: 699fd4413e071a9377369a383c9fd379a3451c6a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Creare o modificare un oggetto contatto telefonico di area comune in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

Per creare oggetti contatto di servizi di dominio Active Directory per tutti i telefoni delle aree comuni, utilizzare il cmdlet **New-CsCommonAreaPhone** . Questo cmdlet può creare nuovi oggetti contatto per l'utilizzo con i telefoni delle aree comuni oppure può associare gli oggetti contatto esistenti a un nuovo telefono di area comune. Per modificare le proprietà degli oggetti contatto associati ai telefoni delle aree comuni, utilizzare il cmdlet **Set-CsCommonAreaPhone** . I parametri facoltativi per **Set-CsCommonAreaPhone** consentono di modificare gli elementi, ad esempio il nome visualizzato di Active Directory del contatto o l'URI (Uniform Resource Identifier) di linea associato al telefono e di abilitare e disabilitare l'account da utilizzare con Lync Server. Per informazioni dettagliate su tutte le modifiche disponibili, vedere la sezione Parameters in [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Per informazioni dettagliate sui parametri **New-CsCommonAreaPhone** , vedere [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

È possibile eseguire questi due cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Creazione di un oggetto contatto telefonico di area comune

  - Per creare un nuovo oggetto contatto telefonico per le aree comuni, utilizzare il cmdlet **New-CsCommonAreaPhone** . Quando si crea un oggetto contatto, è necessario fornire almeno le informazioni seguenti:
    
      - **LineUri**: il numero di telefono assegnato al telefono di area comune. Tenere presente che è necessario utilizzare il formato E. 164 quando si specifica il numero di telefono.
    
      - **RegistrarPool**: il nome di dominio completo (FQDN) del pool di registrazione che ospiterà l'oggetto contatto.
    
      - **Ou**: nome distinto del contenitore di Active Directory in cui verrà creato l'oggetto contatto.
    
    È inoltre consigliabile fornire un nome visualizzato di servizi di dominio Active Directory. In caso contrario, sarà necessario utilizzare un GUID per specificare l'identità del telefono. Ad esempio:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Modifica di un oggetto contatto telefonico di area comune

  - Per modificare le proprietà di un telefono di area comune esistente, utilizzare il cmdlet **Set-CsCommonAreaPhone** . Ad esempio, questo comando configura l'indirizzo SIP per il telefono di area comune con la lobby DisplayName:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) e il cmdlet [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

