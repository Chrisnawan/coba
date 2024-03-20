#include <iostream>
#include <cstdlib>
#define max 10
#include <stdio.h>
using namespace std;

struct Tumpukan{
	int atas;
	int data[max];
}T;

void awal (){
	T.atas=-1;
}
int kosong(){
	if(T.atas==-1)
		return 1;
	else
		return 0;
}

int penuh(){
	if (T.atas == -1)
		return 1;
	else
		return 0;
}

void input (int data){
	if (penuh()==0){
		T.atas++;
		T.data[T.atas]=data;
		cout<<"Data "<<T.data[T.atas]<<"Masuk ke stack";
	}
	else
		cout<<"Tumpukan penuh";
}

void hapus(){
	if (kosong()==0){
		cout<<"Data teratas sudah terambil";
	}
	else
		cout<<"Data kosong";
}

void tampil(){
	if(kosong()==0){
		for(int i=T.atas;i>=0;i--){
			cout<<"\nTumpukan ke"<<i<<"="<<T.data[i];
		}
	}
	else
		cout<<"Tumpukan kosong";
}

void bersih(){
	T.atas =-1;
	cout<<"Tumpukan Kosong";
}

struct Mahasiswa{
		string kelas;
		string nim;
		string nama;
	};

int main(){
	struct Mahasiswa mhs1;
	int pil,data;
	awal();
	do{
		cout<<"1.input\n2.Hapus\n3.Tampil\n4.Bersihkan\n5.Keluar\n:";
		cin >>pil;
		switch(pil){
			case 1: input(data);
				cout<<"Nama: ";
				getline(cin,mhs1.nama);
				cout<<"\nNIM: ";
				getline(cin,mhs1.nim);
				cout<<"\nKelas: ";
				getline(cin,mhs1.kelas);
				break;
			break;
			case 2: hapus();
			break;
			case 3: tampil();
			break;
			case 4: bersih();
			break;
			case 5: cout<<"Terima kasih";
		}
		getchar();
		cout<<endl;
		cout<<endl;
	}
	while (pil!=5);
}

