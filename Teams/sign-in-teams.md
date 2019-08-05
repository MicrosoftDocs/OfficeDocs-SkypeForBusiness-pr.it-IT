---
title: Accedere a Microsoft teams con l'autenticazione moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Come accedere a Microsoft teams con l'autenticazione moderna.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc79f6913a2996734b34d589f124c440eb9835e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180692"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Accedere a Microsoft teams con l'autenticazione moderna
==========================

Microsoft teams USA l'autenticazione moderna per rendere semplice e sicura l'esperienza di accesso. Per vedere come gli utenti possono accedere a teams, leggere [accedere a teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Funzionamento dell'autenticazione moderna

L'autenticazione moderna è un processo che consente ai team di sapere che gli utenti hanno già immesso le proprie credenziali (come la posta elettronica e la password del lavoro) altrove e che non dovrebbero essere necessarie per immetterle di nuovo per avviare l'app. L'esperienza varia a seconda di un paio di fattori, ad esempio se gli utenti lavorano in Windows o in un Mac. Inoltre, a seconda che l'organizzazione abbia abilitato l'autenticazione a singolo fattore o l'autenticazione a più fattori (l'autenticazione a più fattori implica in genere la verifica delle credenziali tramite un telefono, il codice univoco, l'immissione di un PIN o presentazione di un'identificazione personale). Ecco una carrellata di ogni scenario di autenticazione moderno.

### <a name="windows-users"></a>Utenti di Windows: 

- Se gli utenti hanno già effettuato l'accesso ad altre app di Office tramite il proprio account aziendale di Office 365, quando avviano i team vengono portati direttamente all'app. Non è necessario che immettino le proprie credenziali.

- Se gli utenti non hanno eseguito l'accesso al proprio account di Office 365 Enterprise in qualsiasi altro punto, quando avviano teams, viene chiesto di specificare l'autenticazione a singolo fattore o a più fattori (SFA o AMF), a seconda di come l'organizzazione ha deciso che desidera processo da richiedere.

- Se gli utenti hanno eseguito l'accesso a un computer collegato a un dominio, quando avviano teams, potrebbe essere richiesto di passare a un altro passaggio di autenticazione, a seconda che l'organizzazione abbia scelto di richiedere l'AMF o se il proprio computer richiede già l'accesso a Mae. Se il proprio computer richiede già l'accesso a Mae, quando aprono teams, l'app viene avviata automaticamente.

### <a name="mac-users"></a>Utenti Mac 

Quando gli utenti avviano teams, il loro computer non potrà tirare le proprie credenziali dall'account aziendale di Office 365 o da qualsiasi altra applicazione di Office. Verrà invece visualizzato un messaggio che richiede l'AFS o l'AMF (a seconda delle impostazioni dell'organizzazione). Quando gli utenti immettono le proprie credenziali, non saranno tenuti a fornire di nuovo. Da quel momento in poi, teams avvia automaticamente ogni volta che sta lavorando nello stesso computer.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Commutazione di account dopo il completamento dell'autenticazione moderna

Se gli utenti stanno lavorando a un computer collegato al dominio (ad esempio, se il tenant ha abilitato Kerberos), non possono cambiare gli account utente dopo aver completato l'autenticazione moderna. Se gli utenti non stanno lavorando a un computer collegato al dominio, possono cambiare account.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Disconnettersi da Microsoft teams dopo aver completato l'autenticazione moderna
Per disconnettersi da teams, gli utenti possono fare clic sull'immagine del profilo nella parte superiore dell'app e **** quindi selezionare Disconnetti. È anche possibile fare clic con il pulsante destro del mouse sull'icona dell'app nella barra delle applicazioni e quindi scegliere **Disconnetti**. Dopo aver disconnettersi da teams, è necessario immettere di nuovo le credenziali per avviare l'app.

## <a name="troubleshooting-modern-authentication"></a>Risoluzione dei problemi di autenticazione moderna

L'autenticazione moderna è disponibile per ogni organizzazione che usa teams, quindi se gli utenti non riescono a completare il processo, potrebbe esserci qualcosa che non va nel dominio o nell'account aziendale di Office 365 dell'organizzazione. 

Per altre informazioni, vedere [perché si verificano problemi di accesso a Microsoft teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

