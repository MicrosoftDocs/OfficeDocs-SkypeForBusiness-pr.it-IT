---
title: Problemi di ricezione di messaggi e chiamate in sistemi legacy in Teams
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
description: Risolvere i problemi relativi alla ricezione di messaggi e chiamate in sistemi legacy
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 002354418c06980600f5cebef035b8480d0f1bef
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235001"
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

Per altre informazioni, vedere Accedere [a Microsoft Teams con l'autenticazione](sign-in-teams.md) moderna.

## <a name="skype-token-revocation"></a>Skype revoca del token

Quando si modifica o si reimposta una password, i client meno recenti non riceveranno messaggi e chiamate fino a un'ora. Per risolvere il problema, riavviare l'app o passare ai client più nuovi.


## <a name="related-topics"></a>Argomenti correlati

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)