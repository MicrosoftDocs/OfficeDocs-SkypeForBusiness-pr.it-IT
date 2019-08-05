---
title: Test di ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eseguire un ripristino di sistema per un server pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188498"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Test di ripristino di emergenza in Skype for Business Server

Eseguire un ripristino di sistema per un server pool di Skype for Business Server per testare il processo di ripristino di emergenza documentato. Questo test simula un errore hardware completo per un server e consente di garantire che le risorse, i piani e i dati siano disponibili per il ripristino. Provare ad avvicendare ogni mese un campo d'azione diverso, così da sottoporre un server diverso o di un'altra attrezzatura al test. 

La pianificazione in base alla quale le organizzazioni svolgono il test del ripristino di emergenza è soggetta a variazioni. È molto importante non ignorare o trascurare l'esecuzione del test del ripristino di emergenza. 

Esportare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server in un file. Questo file, tra le altre cose, può essere utilizzato per ripristinare le informazioni incluse nell'archivio di gestione centrale dopo una perdita di dati conseguente a un aggiornamento, un errore hardware o altri problemi.

Importare la topologia, i criteri e le impostazioni di configurazione di Skype for Business Server in Central Management Store o nel computer locale, come illustrato nei comandi seguenti: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Per eseguire il backup dei dati di produzione:

- Eseguire il backup dei database RTC e LCSLog usando il processo di backup standard di SQL Server per scaricare il database in un file o un dispositivo di dump del nastro.
- Utilizzare applicazioni di terze parti per eseguire il backup dei dati in file o su nastro.
- Creare un file di esportazione XML dell'intero database RTC utilizzando il cmdlet Export-CsUserData.
- Usare il backup del file System o il backup di terze parti per eseguire il backup di contenuto della riunione e registri di conformità.
- Usare lo strumento della riga di comando Export-CsConfiguration per eseguire il backup delle impostazioni di Skype for Business Server.

Il primo passaggio della procedura di failover prevede lo spostamento forzato di utenti dal pool di produzione al pool del ripristino di emergenza. Lo spostamento è forzato poiché il pool di produzione non ammette il riposizionamento degli utenti.

Il processo utente di trasferimento di Skype for Business Server è effettivamente una modifica a un attributo dell'oggetto account utente oltre a un aggiornamento di record nel database SQL RTC. Questi dati possono essere ripristinati dal dispositivo di dump del backup originale dalla versione di SQL Server di produzione usando il processo di ripristino standard di SQL Server oppure usando un'utilità di backup/ripristino di terze parti.

Dopo il ripristino di questi dati, gli utenti possono connettersi efficacemente al pool di ripristino di emergenza e operare come di consueto. Per consentire agli utenti di connettersi al pool di ripristino di emergenza, sarà necessaria una modifica del record DNS.

I client che usano il pool di Skype for business di produzione verranno referenziati usando i record SRV di configurazione automatica e DNS di:

- SRV: _sip. _tls. \<dominio>/CNAME: SIP. \<> di dominio
- CNAME: SIP. \<dominio>/CVC-pool-1. \<> di dominio

Per agevolare il failover, il record CNAME deve essere aggiornato in modo che faccia riferimento all'FQDN DROCSPool:

- CNAME: SIP.<domain> /DROCSPool. \<> di dominio
- SIP. \<> di dominio
- > AV\<. Domain
- webconf. \<> di dominio
