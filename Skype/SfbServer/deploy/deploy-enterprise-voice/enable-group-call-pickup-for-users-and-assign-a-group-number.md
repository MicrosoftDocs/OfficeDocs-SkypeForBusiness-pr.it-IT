---
title: Abilitare la risposta alle chiamate di gruppo per gli utenti e assegnare un numero di gruppo in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Abilitare gli utenti per la risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale e assegnare un numero di gruppo.
ms.openlocfilehash: 3467aea1b9671a93cca2f66a2ac73c39f15dc26e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830966"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>Abilitare la risposta alle chiamate di gruppo per gli utenti e assegnare un numero di gruppo in Skype for Business

Abilitare gli utenti per la risposta alle chiamate di gruppo in Skype for Business Server VoIP aziendale e assegnare un numero di gruppo.

Dopo aver aggiunto i numeri del gruppo di prelievo chiamata alla tabella orbit del parcheggio di chiamata, si utilizza lo strumento SEFAUtil per assegnare i numeri di gruppo agli utenti e abilitare la risposta alle chiamate di gruppo.

> [!NOTE]
> In una distribuzione ibrida non assegnare un gruppo di risposta alle chiamate di gruppo agli utenti ospitati online. Gli utenti ospitati online non possono partecipare alla risposta alle chiamate di gruppo. In altre parole, le chiamate non possono essere effettuate da altri utenti e non possono rispondere alle chiamate ad altri utenti.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Per assegnare un numero di gruppo e abilitare la risposta alle chiamate di gruppo per un utente

1. Accedere al computer in cui è stato installato lo strumento SEFAUtil con diritti di amministratore.

2. Nella riga di comando digitare il comando seguente:

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    Ad esempio, per assegnare il numero di gruppo 199 a un utente:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>Vedere anche

[Disabilitare la prelievo gruppo per gli utenti](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

