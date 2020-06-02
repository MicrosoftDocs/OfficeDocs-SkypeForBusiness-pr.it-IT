---
title: Problemi di ricezione di messaggi e chiamate su sistemi legacy in teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
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
description: Risolvere i problemi relativi alla ricezione dei messaggi e alle chiamate nei sistemi legacy
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489161"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemi di ricezione di messaggi e chiamate su sistemi legacy
==============================================================

Gli utenti potrebbero avere problemi a ricevere messaggi o chiamate se usano versioni precedenti di team o hanno effettuato l'accesso con altre applicazioni.

## <a name="legacy-adu-setups"></a>Configurazioni ADU legacy

 Se gli utenti hanno eseguito l'accesso a un computer aggiunto a un dominio e **non si vuole che il nome utente sia precompilato nella schermata di accesso a Teams**, gli amministratori possono impostare la chiave seguente del Registro di sistema di Windows per disattivare il prepopolamento del nome utente (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> La precompilazione del nome utente per i nomi che terminano in ".local" o ".corp" è disattivata per impostazione predefinita, non è necessario impostare una chiave del Registro di sistema allo scopo.

Per altre informazioni, vedere [accedere a Microsoft teams con l'autenticazione moderna](sign-in-teams.md) .

## <a name="skype-token-revocation"></a>Revoca token Skype

Quando si cambia/si reimposta una password, i client meno recenti non riceveranno messaggi e richiederanno fino a un'ora. Per risolvere il problema, riavviare l'app o passa a client più recenti.
