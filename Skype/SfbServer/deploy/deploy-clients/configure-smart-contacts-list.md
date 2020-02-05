---
title: Configurare l'elenco contatti intelligenti nei client Skype for business
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
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Riepilogo: informazioni su come attivare la caratteristica elenco contatti Smart nel client Skype for business.'
ms.openlocfilehash: 9db4e6616aa4c11be3ad2f9ee1cd92a0587b4e51
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768869"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurare l'elenco contatti intelligenti nei client Skype for business

**Riepilogo:** Informazioni su come attivare la caratteristica elenco contatti intelligenti nel client Skype for business.

La caratteristica elenco contatti intelligenti consente la popolazione automatica degli elenchi di contatti per gli utenti finali. Al primo utilizzo di Skype for business, gli utenti vedranno automaticamente il loro manager e altre persone nel loro team. Questa caratteristica è attivata per impostazione predefinita per gli utenti di Office 365, ma è necessario abilitare esplicitamente questa caratteristica per gli utenti locali configurando l'impostazione del criterio client.

Quando si configura questa funzionalità, tieni presente quanto segue:

- Gli utenti, fino a 13, vengono aggiunti automaticamente all'elenco contatti intelligenti nell'ordine seguente:

  1. Manager

  2. Dirige in ordine alfabetico

  3. Peer in ordine alfabetico

- La prima volta che si accede a un utente, viene creato un nuovo gruppo denominato gruppo personale. Il gruppo viene popolato automaticamente con persone nella relazione del gruppo di annunci dell'utente in base all'alias utente compilato nel campo Manager. Tieni presente che le modifiche apportate all'appartenenza al gruppo di annunci non causano aggiornamenti al gruppo dopo che è stato inizialmente compilato. Se un utente elimina un contatto o il gruppo, non vengono ricreati né il contatto né il gruppo. 

- Se il contrassegno automatico è attivato, i contatti nell'elenco verranno contrassegnati per le modifiche alla presenza. La codifica automatica è attivata per impostazione predefinita, ma puoi scegliere di disattivarla. 

- Tutti i nuovi utenti del gruppo verranno informati che sono stati aggiunti all'elenco contatti. Gli utenti possono aggiungere manualmente nuovi membri al gruppo personale o ad altri gruppi di loro scelta.

- Questa funzionalità funziona solo per gli utenti che accedono per la prima volta. Se un utente ha già eseguito l'accesso da qualsiasi dispositivo, ad esempio un dispositivo mobile o un Mac, la funzionalità non è abilitata per l'utente.

## <a name="configure-smart-contacts-list"></a>Configurare l'elenco contatti intelligente

Per abilitare la caratteristica elenco contatti Smart per gli utenti, è necessario eseguire la procedura seguente: 

- Creare una nuova voce di CsClientPolicy e aggiungerla al criterio client globale. 

- Verificare che la ricerca della rubrica sia configurata solo per la ricerca Web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Creare una voce di criteri per abilitare l'elenco contatti intelligenti

Per creare una voce di criteri per abilitare la caratteristica elenco contatti intelligenti, usare il cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con l'opzione EnableClientAutoPopulateWithTeam come indicato di seguito:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Utilizzare quindi il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) per scrivere le modifiche apportate al criterio globale nel modo seguente:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

È possibile creare facoltativamente un criterio per disattivare la codifica automatica come indicato di seguito:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Devi anche impostare il parametro AddressBookAvailability per il criterio corrispondente in WebSearchOnly. Per altre informazioni, vedere [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Risoluzione dei problemi

Se l'elenco contatti intelligenti non funziona come previsto, verificare quanto segue:

- Convalidare la configurazione. 

- Verificare che le informazioni sull'organizzazione degli annunci vengano popolate.

- Raccogliere i registri client Skype for business su un nuovo utente per un'ulteriore analisi.

- Verificare che l'interfaccia utente del client Skype for business non visualizzi un messaggio che non riesce a connettersi alla Rubrica. Per confermare la connettività della Rubrica, eseguire una ricerca per un utente nella barra di ricerca del client Skype for business.

- I problemi di replica di servizi di dominio Active Directory possono causare la risoluzione dei contatti quando un utente accede prima a Skype for business.


