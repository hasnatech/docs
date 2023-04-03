# Accordion

## HTML
    <div class="col-lg-2" *ngFor="let item of drowdown; let i = index">
        <div>
            <div class="dropdown_btn" (click)="toggleMenu(i)">
                <div>
                    <p class="m-0">{{item.header}}</p>
                </div>
                <div [class.d_arrow_transform]="showMenu[i]">
                    <img src="assets/down_arrow.svg" alt="">
                </div>
            </div>
            <div *ngFor="let child of item.child; let j = index">
                <div class="values" *ngIf="showMenu[i] == true">
                    <p class="m-0 cursor" (click)="selectedDrop(i, j, child)">
                        {{child.value}} 
                        - {{item.selected}}
                    </p>
                </div>
            </div>
        </div>
    </div>
