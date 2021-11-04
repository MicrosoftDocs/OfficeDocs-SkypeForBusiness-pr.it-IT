---
title: Problemi di ricezione di messaggi e chiamate in sistemi legacy in Teams
ms.reviewer: ''
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Risolvere i problemi relativi alla ricezione di messaggi e chiamate in sistemi legacy
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fb36f4be70b174a324f017b1e52529f457e83f36
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768304"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemi di ricezione di messaggi e chiamate in sistemi legacy

Gli utenti potrebbero avere problemi a ricevere messaggi o chiamate se usano versioni precedenti di Teams o se hanno eseguito l'accesso con altre applicazioni.

## <a name="legacy-adu-setups"></a>Configurazioni ADU legacy

 Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio e **non si vuole che il nome utente sia precompilato nella schermata di accesso a Teams**, gli amministratori possono impostare la chiave seguente del Registro di sistema di Windows per disattivare il prepopolamento del nome utente (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> La precompilazione del nome utente per i nomi che terminano in ".local" o ".corp" è disattivata per impostazione predefinita, non è necessario impostare una chiave del Registro di sistema allo scopo.

Per altre informazioni, vedere Accedere [Microsoft Teams con l'autenticazione](sign-in-teams.md) moderna.

## <a name="skype-token-revocation"></a>Skype revoca del token

Quando si modifica o si reimposta una password, i client meno recenti non riceveranno messaggi e chiamate fino a un'ora. Per risolvere il problema, riavviare l'app o passare ai client più nuovi.


## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)