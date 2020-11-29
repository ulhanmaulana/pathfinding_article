PATH FINDING DI UNITY DENGAN MENGGUNAKAN FITUR NAVIGASI
1.	Buat objek, plane, tembok, player, dan musuh



[My image](ulhanmaulana.github.com/pathfinding_article/1.jpg)













2.	Beri warna pada objek player dan musuh
























3.	Klik window-navigation






























4.	Seleksi semua tembok dan centang navigation static pada tab navigation-> object












5.	Lalu masuk ke tab bake dan klik tombol bake

















6.	Buat script baru dengan nama NPCmove dan berikut isinya

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.AI;

public class NPCmove : MonoBehaviour {

    [SerializeField]
    Transform _destination;

    NavMeshAgent _navMeshAgent;

    void Start()
    {
        _navMeshAgent = this.GetComponent<NavMeshAgent> ();
        if (_navMeshAgent == null) {
            Debug.LogError ("the nav mesh agent component is not attached  to " + gameObject.name);
        }
        else 
        {
            SetDestination ();
        }
    }
    private void SetDestination ()
    {
        if(_destination != null)
        {
            Vector3 targetVector = _destination.transform.position;
            _navMeshAgent.SetDestination (targetVector);
        }
    }
}


7.	Masukkan script tersebut pada objek musuh, dan berikan juga rigidbody dan navmesh agent






















8.	Isikan atribut destination dengan object player
9.	play
