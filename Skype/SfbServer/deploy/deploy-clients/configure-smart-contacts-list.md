---
title: Configurare l'elenco dei contatti intelligenti nei client Skype for business
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
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Riepilogo: informazioni su come abilitare la funzionalità elenco contatti Smart nel client Skype for business.'
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805776"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>Configurare l'elenco dei contatti intelligenti nei client Skype for business

**Riepilogo:** Informazioni su come abilitare la funzionalità elenco contatti Smart nel client Skype for business.

La funzionalità elenco contatti avanzati consente la popolamento automatico degli elenchi di contatti per gli utenti finali. Al primo utilizzo di Skype for business, gli utenti visualizzeranno automaticamente il Manager e altre persone del team. Questa funzionalità è attivata per impostazione predefinita per gli utenti di Microsoft 365 e Office 365, ma è necessario abilitare esplicitamente questa funzionalità per gli utenti locali configurando l'impostazione dei criteri client.

Quando si configura questa funzionalità, tenere presente quanto segue:

- Gli utenti, fino a 13, vengono aggiunti automaticamente all'elenco dei contatti Smart nell'ordine seguente:

  1. Manager

  2. Indirizza in ordine alfabetico

  3. Peer in ordine alfabetico

- La prima volta che un utente esegue l'accesso, viene creato un nuovo gruppo denominato My Group. Il gruppo viene popolato automaticamente con persone nella relazione del gruppo di annunci dell'utente in base all'alias utente popolato nel campo Manager. Si noti che le modifiche apportate all'appartenenza a un gruppo di annunci non causano aggiornamenti al gruppo dopo che è stata inizialmente popolata. Se un utente elimina un contatto o un gruppo, il contatto o il gruppo non vengono ricreati. 

- Se l'opzione di tagging automatico è attivata, i contatti nell'elenco verranno contrassegnati per le modifiche alla presenza. La codifica automatica è attivata per impostazione predefinita, ma è possibile scegliere di disattivarla. 

- Tutti i nuovi utenti del gruppo verranno informati che sono stati aggiunti all'elenco dei contatti. Gli utenti possono aggiungere manualmente nuovi membri al proprio gruppo personale o ad altri gruppi di loro scelta.

- Questa funzionalità è compatibile solo per gli utenti che accedono per la prima volta. Se un utente ha precedentemente eseguito l'accesso da qualsiasi dispositivo, ad esempio un dispositivo mobile o un Mac, la caratteristica non è abilitata per l'utente.

## <a name="configure-smart-contacts-list"></a>Configurare l'elenco contatti intelligente

Per abilitare la funzionalità elenco contatti Smart per gli utenti, è necessario eseguire le operazioni seguenti: 

- Creare una nuova voce di CsClientPolicy e aggiungerla al criterio client globale. 

- Verificare che la ricerca rubrica sia configurata solo per la ricerca Web.

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>Creare una voce di criteri per abilitare l'elenco dei contatti intelligenti

Per creare una voce di criteri per abilitare la funzionalità elenco Smart contacts, utilizzare il cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con l'opzione EnableClientAutoPopulateWithTeam, come indicato di seguito:

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

Successivamente, utilizzare il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) per scrivere le modifiche apportate ai criteri globali, come indicato di seguito:

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

Facoltativamente, è possibile creare un criterio per disattivare il tagging automatico come indicato di seguito:

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

È inoltre necessario impostare il parametro AddressBookAvailability per il criterio corrispondente su WebSearchOnly. Per ulteriori informazioni, vedere [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 

### <a name="troubleshoot"></a>Risoluzione dei problemi

Se l'elenco dei contatti avanzati non funziona come previsto, controllare quanto segue:

- Convalidare la configurazione. 

- Verificare che le informazioni dell'organizzazione di Active Directory siano popolate.

- Raccolta di registri client Skype for business su un nuovo utente per ulteriori analisi.

- Verificare che l'interfaccia utente del client Skype for business non visualizzi un messaggio che non sia in grado di connettersi alla Rubrica. Per confermare la connettività della Rubrica, eseguire una ricerca per un utente nella barra di ricerca del client Skype for business.

- I problemi di replica di servizi di dominio Active Directory potrebbero causare la risoluzione dei contatti quando un utente accede per la prima volta a Skype for business.


