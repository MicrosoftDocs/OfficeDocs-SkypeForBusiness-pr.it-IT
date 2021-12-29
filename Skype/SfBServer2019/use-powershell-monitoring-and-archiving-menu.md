---
title: Usare PowerShell per le attività del menu Monitoraggio e archiviazione
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Riepilogo: Skype for Business Server pannello di controllo al mapping cmdlet per il menu Monitoraggio e archiviazione.'
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626232"
---
# <a name="monitoring-and-archiving"></a>Monitoraggio e archiviazione

In questo articolo viene descritto come ottenere risultati simili a quelli della voce di **menu** Monitoraggio e archiviazione nel Pannello di controllo legacy utilizzando i cmdlet.

In questo articolo vengono descritti i sottomenu seguenti:

- [Monitoraggio e archiviazione](#monitoring-and-archiving)
  - [Registrazione dettagli chiamata](#call-detail-recording)
  - [Dati sulla qualità dell'esperienza](#quality-of-experience-data)
  - [Criteri archiviazione](#archiving-policy)
  - [Configurazione archiviazione](#archiving-configuration)

## <a name="call-detail-recording"></a>Registrazione dettagli chiamata

**Il sottomenu REGISTRAZIONE DETTAGLI** CHIAMATA consente agli amministratori di gestire le impostazioni di registrazione dettagli chiamata (CDR). CdR consente di tenere traccia dell'utilizzo di elementi quali sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza.

Prendiamo in considerazione le varie attività che un utente può eseguire su **CALL DETAIL RECORDING** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutte le configurazioni di registrazione dei dati

   ![List Cdr Configuration](./media/cdr-configurations-1.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Esempio***

```powershell
 Get-CsCdrConfiguration
```

---

> **Scenario 2:** creare una nuova configurazione di registrazione registrazione dati

   ![Creare la configurazione cdr](./media/cdr-configurations-2.png)

***Cmdlet***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***Esempio***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **Scenario 3**: ottenere i dettagli di una configurazione di registrazione dettagli dettagli windows scelta

   ![Get Cdr Configuration](./media/cdr-configurations-3.png)

***Cmdlet***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Esempio***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare le configurazioni di registrazione dei dati selezionate

   ![Delete Cdr Configuration](./media/cdr-configurations-4.png)

***Cmdlet***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***Esempio***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare una configurazione di registrazione dei dati

   ![Aggiornare la configurazione cdr](./media/cdr-configurations-5.png)

***Cmdlet***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***Esempio***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>Dati sulla qualità dell'esperienza

Il **sottomenu QUALITY OF EXPERIENCE DATA** consente agli amministratori di gestire le impostazioni QoE (Quality of Experience). in tutta l'organizzazione; ciò include la gestione dell'espansione del gruppo, delle impostazioni dei certificati e dei metodi di autenticazione consentiti. Poiché gli amministratori possono configurare impostazioni diverse nell'ambito globale, del sito e del servizio (anche se solo per il servizio Servizi Web), è possibile personalizzare le funzionalità dei servizi Web per utenti diversi e posizioni diverse.

Prendere in considerazione le varie attività che un utente può eseguire su **WEB SERVICE** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutte le configurazioni QoE

   ![Elencare la configurazione QoE](./media/qoe-configuration-1.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Esempio***

```powershell
 Get-CsQoEConfiguration
```

---

> **Scenario 2:** creare una nuova configurazione QoE

   ![Nuova configurazione QoE](./media/qoe-configuration-2.png)

***Cmdlet***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***Esempio***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **Scenario 3:** ottenere i dettagli di una configurazione QoE scelta

   ![Ottenere la configurazione QoE](./media/qoe-configuration-3.png)

***Cmdlet***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Esempio***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare le configurazioni QoE scelte

   ![Eliminare la configurazione QoE](./media/qoe-configuration-4.png)

***Cmdlet***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***Esempio***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare una configurazione QoE

   ![Aggiornare la configurazione QoE](./media/qoe-configuration-5.png)

***Cmdlet***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***Esempio***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>Criteri archiviazione

Gli amministratori possono utilizzare **criteri di archiviazione** per gestire i criteri di archiviazione delle sessioni di messaggistica istantanea. I criteri di archiviazione consentono di archiviare tutte le sessioni di messaggistica istantanea e web conferencing che si svolgono tra utenti interni e/o tra utenti interni ed utenti esterni

Prendere in considerazione le varie attività che un utente può eseguire sui criteri di archiviazione e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i criteri di archiviazione

   ![Criteri di archiviazione elenco](./media/archiving-policy-1.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Esempio***

```powershell
 Get-CsArchivingPolicy
```

---

> **Scenario 2:** creare un nuovo criterio di archiviazione

   ![Creare criteri di archiviazione](./media/archiving-policy-2.png)

***Cmdlet***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***Esempio***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **Scenario 3:** ottenere i dettagli di un criterio di archiviazione scelto

   ![Ottenere criteri di archiviazione](./media/archiving-policy-3.png)

***Cmdlet***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Esempio***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare i criteri di archiviazione scelti

   ![Elimina criteri di archiviazione](./media/archiving-policy-4.png)

***Cmdlet***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***Esempio***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare un criterio di archiviazione

   ![Aggiornare i criteri di archiviazione](./media/archiving-policy-5.png)

***Cmdlet***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***Esempio***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>Configurazione archiviazione

Gli amministratori possono **utilizzare LA CONFIGURAZIONE DI** ARCHIVIAZIONE per configurare come (o se) le sessioni di messaggistica istantanea vengono archiviate nell'organizzazione.

Prendere in considerazione le varie attività che un utente può eseguire su **ARCHIVING CONFIGURATION** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutte le configurazioni di archiviazione

   ![Configurazione archiviazione elenchi](./media/archiving-configuration-1.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Esempio***

```powershell
 Get-CsArchivingConfiguration
```

---

> **Scenario 2:** creare una nuova configurazione di archiviazione

   ![Creare la configurazione di archiviazione](./media/archiving-configuration-2.png)

***Cmdlet***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***Esempio***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **Scenario 3:** ottenere i dettagli di una configurazione di archiviazione scelta

   ![Ottenere la configurazione di archiviazione](./media/archiving-configuration-3.png)

***Cmdlet***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Esempio***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare le configurazioni di archiviazione scelte

   ![Elimina configurazione di archiviazione](./media/archiving-configuration-4.png)

***Cmdlet***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***Esempio***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare una configurazione di archiviazione

   ![Aggiornare la configurazione di archiviazione](./media/archiving-configuration-5.png)

***Cmdlet***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***Esempio***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---
