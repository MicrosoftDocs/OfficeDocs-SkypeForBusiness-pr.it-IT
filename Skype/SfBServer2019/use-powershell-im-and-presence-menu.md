---
title: Usare PowerShell per le attività del menu Messaggistica istantanea e presenza
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
description: 'Riepilogo: Skype for Business Server pannello di controllo al mapping cmdlet per la messaggistica istantanea e il menu Presenza.'
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888756"
---
# <a name="im-and-presence"></a>Messaggistica istantanea e presenza

In questo articolo viene descritto come ottenere risultati simili a quelli della voce di **menu** Messaggistica istantanea e Presenza nel Pannello di controllo legacy utilizzando i cmdlet.

In questo articolo vengono descritti i sottomenu seguenti:

- [Messaggistica istantanea e presenza](#im-and-presence)
  - [Filtro file](#file-filter)
  - [Filtro URL](#url-filter)

## <a name="file-filter"></a>Filtro file

**Il** sottomenu FILTRO FILE consente agli amministratori di gestire le configurazioni del filtro di trasferimento file nell'organizzazione. Queste configurazioni vengono utilizzate per bloccare la capacità di un utente di trasferire determinati tipi di file (ad esempio, file con estensione vbs o .ps1) utilizzando un client Skype for Business Server.

Prendere in considerazione le varie attività che un utente può eseguire su **FILE FILTER** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i filtri di file

   ![Filtro file elenco](./media/file-filter-1.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Esempio***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **Scenario 2:** creare un nuovo filtro file

   ![Creare un filtro file](./media/file-filter-2.png)

***Cmdlet***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***Esempio***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Scenario 3:** ottenere i dettagli di un filtro file scelto

   ![Get File Filter](./media/file-filter-3.png)

***Cmdlet***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Esempio***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare i filtri di file scelti

   ![Elimina filtro file](./media/file-filter-4.png)

***Cmdlet***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***Esempio***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare un filtro file

   ![Aggiorna filtro file](./media/file-filter-5.png)

***Cmdlet***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***Esempio***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>Filtro URL

La **voce del** sottomenu FILTRO URL in Messaggistica istantanea e presenza consente agli amministratori di configurare il filtro URL in modo che i collegamenti ipertestuali con determinati prefissi siano bloccati o non siano attivi.  In altre parole, i partecipanti non possono semplicemente fare clic sul collegamento e passare al sito a cui fa riferimento l'URI, ma devono copiare e incollare manualmente il collegamento in un browser.

Prendiamo in considerazione le varie attività che un utente può eseguire su **FILTRO URL** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutti i filtri URL Web

   ![Filtro URL elenco](./media/url-filter-1.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Esempio***

```powershell
 Get-CsImFilterConfiguration
```

---

> **Scenario 2:** creare un nuovo filtro URL

   ![Nuovo filtro URL](./media/url-filter-2.png)

***Cmdlet***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***Esempio***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Scenario 3:** ottenere i dettagli di un filtro URL scelto

   ![Ottenere il filtro URL](./media/url-filter-3.png)

***Cmdlet***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Esempio***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Scenario 4**: Eliminare i filtri URL scelti

   ![Elimina filtro URL](./media/url-filter-4.png)

***Cmdlet***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***Esempio***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Scenario 5:** aggiornare un filtro URL

   ![Aggiornare il filtro URL](./media/url-filter-5.png)

***Cmdlet***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***Esempio***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---
