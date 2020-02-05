---
title: Abilitare il ritiro delle chiamate di gruppo per gli utenti e assegnare un numero di gruppo in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: Abilitare gli utenti per il ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale e assegnare un numero di gruppo.
ms.openlocfilehash: bebddb5f71612cf23d442366c774d0e8d4b9f500
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767269"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Abilitare il ritiro delle chiamate di gruppo per gli utenti e assegnare un numero di gruppo in Skype for business

Abilitare gli utenti per il ritiro delle chiamate di gruppo in Skype for Business Server VoIP aziendale e assegnare un numero di gruppo.

Dopo aver aggiunto i numeri di gruppo di prelievo chiamate alla tabella Orbit di Call Park, è possibile usare lo strumento SEFAUtil per assegnare i numeri di gruppo agli utenti e abilitare il ritiro delle chiamate di gruppo.

> [!NOTE]
> In una distribuzione ibrida non assegnare un gruppo di raccolta chiamate di gruppo agli utenti ospitati online. Gli utenti ospitati online non possono partecipare al ritiro delle chiamate di gruppo. Ossia, non è possibile rispondere alle chiamate di altri utenti, e non possono ricevere risposte ad altri utenti.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Per assegnare un numero di gruppo e abilitare il ritiro delle chiamate di gruppo per un utente

1. Accedere al computer in cui è stato installato lo strumento SEFAUtil con i diritti di amministratore.

2. Nella riga di comando eseguire:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Ad esempio, per assegnare un numero di gruppo 199 a un utente:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Vedere anche

[Disabilitare il prelievo di gruppo per gli utenti](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

