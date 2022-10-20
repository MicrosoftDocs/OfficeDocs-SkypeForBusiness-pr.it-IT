---
title: Numeri di telefono e modifiche alle licenze
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: Scopri in che modo le modifiche alle licenze possono influire sulla gestione dei numeri di telefono.
ms.openlocfilehash: e023c1606157a5beeafedfa358e470555ba7f653
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614319"
---
# <a name="how-licensing-affects-phone-number-management"></a>Influenza delle licenze sulla gestione dei numeri di telefono

La modalità di rimozione e assegnazione di licenze agli utenti può influire sulla capacità di un utente di effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) in Microsoft Teams. Questo articolo descrive come gestire le modifiche delle licenze per garantire che la capacità degli utenti di effettuare e ricevere chiamate PSTN non sia influenzata.

Per informazioni generali sulla gestione dei numeri di telefono, vedi [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-landing-page.md). Per informazioni generali sulle licenze per i componenti aggiuntivi di Teams, vedere [Licenze per i componenti aggiuntivi di Microsoft Teams](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md).



## <a name="remove-a-license"></a>Rimuovere una licenza

Se si dispone di un utente con un numero di telefono assegnato e si rimuovono una o più licenze dei prerequisiti, la rimozione della licenza comporta anche l'annullamento dell'assegnazione del numero di telefono dall'utente. Senza un numero di telefono assegnato, la capacità dell'utente di effettuare e ricevere chiamate PSTN in Microsoft Teams è influenzata.

A seconda dell'opzione di [connettività PSTN](pstn-connectivity.md) dell'utente, la rimozione di una licenza ha il seguente impatto sui parametri di telefonia:

- **La rimozione di una licenza per un piano per chiamate Microsoft 365 da un utente con un numero di telefono del piano per chiamate** :
  - Copiare qualsiasi valore in OnPremLineUri in LineUri
  - Impostare EnterpriseVoiceEnabled su False
  - Impostare lo stato di assegnazione dei numeri di telefono su Non assegnato nel database dei numeri di telefono


- **La rimozione di una licenza Sistema telefonico Microsoft 365 da un utente con un numero di telefono Operator Connect** :
  - Cancella LineUri
  - Impostare EnterpriseVoiceEnabled su False
  - Impostare lo stato di assegnazione del numero di telefono su Non assegnato nel database dei numeri di telefono


- **La rimozione di una licenza Sistema telefonico Microsoft 365 da un utente con un numero di telefono Direct Routing** :
  - Cancella LineUri
  - Impostare EnterpriseVoiceEnabled su False
  - Rimuovere il numero di telefono dal database dei numeri di telefono


## <a name="change-a-license"></a>Cambiare una licenza

Se è necessario modificare una licenza per un utente che implica una delle licenze prerequisite, è necessario assicurarsi che le modifiche alle licenze vengano apportate e salvate contemporaneamente. Questo metodo garantisce che l'utente mantenga il numero di telefono assegnato e possa continuare a effettuare e ricevere chiamate PSTN in Microsoft Teams. 

Si supponga, ad esempio, di voler assegnare una licenza di Microsoft 365 E5 a un utente che dispone attualmente di una licenza di Microsoft 365 E3. 

- Se si usa l'interfaccia di amministrazione di Teams, nella scheda **Licenze e app** dei dettagli dell'utente assicurarsi che la licenza precedente venga rimossa e che la nuova licenza venga aggiunta prima di fare clic su **Salva modifiche**. 

- Se si usano i cmdlet di PowerShell [, Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) o [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense), eseguire il cmdlet una volta e utilizzare sia i parametri -AddLicenses che -RemoveLicenses.

Se rimuovi la vecchia licenza e salvi la modifica, quindi aggiungi la nuova licenza e salvi la modifica, il numero di telefono non sarà assegnato e l'utente potrebbe perdere la possibilità di effettuare e ricevere chiamate PSTN in Microsoft Teams. Dopo aver assegnato la nuova licenza, dovrai riassire il numero di telefono all'utente.










