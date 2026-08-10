

```ts
@Component({
  selector: 'app-root',
  imports: [ MatTableModule, MatPaginatorModule],
  templateUrl: './app.html',
  styleUrl: './app.css'
})

export class App implements OnInit, AfterViewInit{

  displayedColumns: string[] = ["id", "name", "email", "phone"];

  dataSource = new MatTableDataSource<any>([])
/* Class provided by Angular Material, special wrapper.  
Properties like dataSource.data, dataSource.paginator,        dataSource.sort, dataSource.filter */


  @ViewChild(MatPaginator)
  paginator!: MatPaginator;

  constructor(private http:HttpClient){};

  ngOnInit(): void {
    this.loadUsers();
  }

  ngAfterViewInit(): void {
    this.dataSource.paginator = this.paginator;
  }

  loadUsers(){
    this.http.get<any[]>('https://jsonplaceholder.typicode.com/users')
    .subscribe({
      next: (response) => {
        this.dataSource.data = response

        if(this.paginator){
          this.dataSource.paginator = this.paginator;
        }
      },
      error: (err) => {
        console.log(err)
      }
    });
  }
}

```

# <center> HTML

```html
<div style="padding:20px">

  <h2>User List</h2>

  <table
    mat-table //directive
    [dataSource]="dataSource" //property binding
    class="mat-elevation-z8" //shadow class
    style="width:100%">

    <ng-container //used to group directives
      matColumnDef="id" //column named "id", 
      //This name must match what's in displayedColumns.
    > 
      <th 
        mat-header-cell    //Material header cell.
        *matHeaderCellDef  //header template
      >
      ID
      </th>

      <td mat-cell *matCellDef="let user">
        {{ user.id }}
      </td>
    </ng-container>

    <!-- Name -->
    <ng-container matColumnDef="name">
      <th mat-header-cell *matHeaderCellDef>Name</th>
      <td mat-cell *matCellDef="let user">
        {{ user.name }}
      </td>
    </ng-container>

    <!-- Email -->
    <ng-container matColumnDef="email">
      <th mat-header-cell *matHeaderCellDef>Email</th>
      <td mat-cell *matCellDef="let user">
        {{ user.email }}
      </td>
    </ng-container>

    <!-- Phone -->
    <ng-container matColumnDef="phone">
      <th mat-header-cell *matHeaderCellDef>Phone</th>
      <td mat-cell *matCellDef="let user">
        {{ user.phone }}
      </td>
    </ng-container>

    <tr mat-header-row *matHeaderRowDef="displayedColumns"></tr>

    <tr
      mat-row
      *matRowDef="let row; columns: displayedColumns">
    </tr>

  </table>

  <mat-paginator
    [pageSize]="5"
    [pageSizeOptions]="[2,5,10]"
    showFirstLastButtons>
  </mat-paginator>

</div>
```