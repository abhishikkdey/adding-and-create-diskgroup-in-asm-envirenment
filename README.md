# adding-and-create-diskgroup-in-asm-envirenment
## adding extra 10 gb in existing diskgroup

'SELECT 
    name,
    state,
    ROUND((total_mb / 1024), 2) AS total_gb,
    ROUND(((total_mb - free_mb) / 1024), 2) AS used_gb, 
    ROUND((1 - (free_mb / NULLIF(total_mb, 0))) * 100, 2) AS pct_used 
FROM v$asm_diskgroup
ORDER BY name;'

<img width="1030" height="360" alt="image" src="https://github.com/user-attachments/assets/784469ca-4007-4c5c-a969-a2c09705b0d2" />

# add extra 10 gb in vm
then command 'fdisk /dev/sdc'

<img width="1021" height="370" alt="image" src="https://github.com/user-attachments/assets/d63e09d7-b5c2-42c5-8966-2f70a56e9c67" />

' oracleasm createdisk DATA2 /dev/sdc1'

from grid user

'alter diskgroup DATA add disk '/dev/oracleasm/disks/DATA2';'


<img width="891" height="163" alt="image" src="https://github.com/user-attachments/assets/ea04a787-4914-4b05-b439-4f59b6a09872" />


<img width="1335" height="198" alt="image" src="https://github.com/user-attachments/assets/2586fbdb-2b7a-4587-8880-a275e0db5858" />

## adding a new diskgroup

'fdisk -l |grep /dev/sd |sort'

<img width="864" height="255" alt="image" src="https://github.com/user-attachments/assets/54c6b3c5-2799-413d-82d2-ea35ebe0a54f" />


<img width="579" height="102" alt="image" src="https://github.com/user-attachments/assets/093ef842-c3f2-4419-97ed-a77c903c5f05" />

'oracleasm createdisk DATA1 /dev/sdd1'

<img width="737" height="76" alt="image" src="https://github.com/user-attachments/assets/11d56b11-7dce-45d6-b149-a9125291a044" />

'oracleasm listdisks;'

<img width="541" height="123" alt="image" src="https://github.com/user-attachments/assets/2632811d-9d35-4763-b2de-cb67e5748862" />

# command to create new diskgroup in oracle

'create diskgroup DATA1 external redundancy disk '/dev/oracleasm/disks/DATA1';

<img width="1095" height="106" alt="image" src="https://github.com/user-attachments/assets/f46817a1-4846-4475-ab1e-41b3145d2947" />


