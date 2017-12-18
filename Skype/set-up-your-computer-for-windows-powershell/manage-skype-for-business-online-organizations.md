---
title: "Gestire Skype for Business Online organizzazioni mediante la Skype per Business Connector Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
description: "Use Windows PowerShell and the Get-CsTenant and Get-CsTenantLicensingConfiguration cmdlets to get information about your Skype for Business Online tenant."
---

# Gestire Skype for Business Online organizzazioni mediante la Skype per Business Connector Online

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
È possibile trovare informazioni del tenant Skype for Business online utilizzando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration**.
  
## Gestire Skype for Business Online tenant

Per restituire le informazioni del tenant Skype for Business online, chiamare il cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) senza parametri aggiuntivi.
  
```
Get-CsTenant
```

Per restituire solo il tenant nome e ID, usare questo comando.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

Il valore del parametro  _TenantID_ è necessario durante l'esecuzione di cmdlet, ad esempio[Set CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e[Impostare CsTenantFederationConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849602).
  
Per trovare informazioni su se le informazioni sulle licenze per il tenant specificato sono disponibile nell'interfaccia di amministrazione di Skype for Business online, utilizzare il cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

