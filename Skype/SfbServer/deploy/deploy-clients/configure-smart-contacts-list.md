---
title: Configurare l'elenco contatti smart nei Skype for Business client
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Riepilogo: informazioni su come attivare la funzionalità Elenco contatti smart nel client Skype for Business smart.'
ms.openlocfilehash: d7e2957b6b8622ea8c3ce3dc2974e7dbb7ff51d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580000"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurare l'elenco contatti smart nei Skype for Business client

**Riepilogo:** Informazioni su come attivare la funzionalità Elenco contatti smart nel client Skype for Business smart.

La funzionalità Elenco contatti smart consente la popolamento automatico degli elenchi di contatti per gli utenti finali. Al primo utilizzo Skype for Business, gli utenti visualizzano automaticamente il manager e altre persone nel team. Questa funzionalità è attivata per impostazione predefinita per gli utenti Microsoft 365 e Office 365, ma è necessario abilitare esplicitamente questa funzionalità per gli utenti locali configurando l'impostazione dei criteri client.

Quando si configura questa funzionalità, tenere presente quanto segue:

- Gli utenti, fino a 13, vengono aggiunti automaticamente all'elenco Contatti smart nell'ordine seguente:

  1. Manager

  2. Indirizza in ordine alfabetico

  3. Peer in ordine alfabetico

- La prima volta che un utente accede, viene creato un nuovo gruppo denominato My Group. Il gruppo viene popolato automaticamente con le persone nella relazione di gruppo AD dell'utente in base all'alias utente popolato nel campo Manager. Tieni presente che le modifiche apportate all'appartenenza al gruppo ad Active Directory non causano aggiornamenti a My Group dopo che è stato inizialmente popolato. Se un utente elimina un contatto o un gruppo, né il contatto né il gruppo vengono ri-creati. 

- Se il tagging automatico è attivato, i contatti nell'elenco verranno contrassegnati per le modifiche alla presenza. Il tagging automatico è attivato per impostazione predefinita, ma puoi scegliere di disattivarlo. 

- Tutti i nuovi utenti del gruppo verranno informati che sono stati aggiunti all'elenco dei contatti. Gli utenti possono aggiungere manualmente nuovi membri al proprio gruppo personale o ad altri gruppi di loro scelta.

- Questa funzionalità è valida solo per gli utenti che a tale scopo esere connessi per la prima volta. Se un utente ha eseguito in precedenza l'accesso da qualsiasi dispositivo, ad esempio qualsiasi dispositivo mobile o Mac, la funzionalità non è abilitata per tale utente.

## <a name="configure-smart-contacts-list"></a>Configurare l'elenco contatti intelligente

Per abilitare la funzionalità Elenco contatti smart per gli utenti, è necessario eseguire la procedura seguente: 

- Creare una nuova voce CsClientPolicy e aggiungerla al criterio client globale. 

- Verificare che la ricerca nella Rubrica sia configurata solo per la ricerca Sul Web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Creare una voce di criterio per abilitare l'elenco contatti smart

Per creare una voce di criterio per abilitare la funzionalità Elenco contatti smart, utilizzare il cmdlet [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con l'opzione EnableClientAutoPopulateWithTeam come segue:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Successivamente, utilizzare il cmdlet [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) per scrivere le modifiche al criterio globale nel modo seguente:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Facoltativamente, puoi creare un criterio per disattivare il tagging automatico come segue:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

È inoltre necessario impostare il parametro AddressBookAvailability per il criterio corrispondente su WebSearchOnly. Per ulteriori informazioni, vedere [Set-CsClientPolicy.](/powershell/module/skype/set-csclientpolicy?view=skype-ps) 

### <a name="troubleshoot"></a>Risoluzione dei problemi

Se l'elenco contatti smart non funziona come previsto, verificare quanto segue:

- Convalidare la configurazione. 

- Verificare che le informazioni sull'organizzazione di Active Directory sono popolate.

- Raccogliere Skype for Business log client su un nuovo utente per un'ulteriore analisi.

- Verificare che l Skype for Business'interfaccia utente del client non visualizza un messaggio che indica che non è in grado di connettersi alla Rubrica. Per verificare la connettività della Rubrica, eseguire una ricerca per un utente nella barra Skype for Business di ricerca del client.

- I problemi di replica di Servizi di dominio Active Directory potrebbero causare i contatti non risolti quando un utente accede per la prima volta a Skype for Business.