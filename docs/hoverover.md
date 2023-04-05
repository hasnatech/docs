## HoverOver

### TS file
    tiles = [
        {
        title: "Be customer driven",
        description: `<p><b>Building strong customer relationships and delivering customer driven
        solutions.</b>
        </p>
        <ul>
            <li>Knows our customers and gains insights into customer needs.</li>
            <li>Identifies opportunities that benefit the customer.</li>
            <li>Builds and delivers solutions that meet customer needs.</li>
            <li>Starts with customers in all aspects of work.</li>
        </ul>`,
        showme: false,
        color: "lblue"
        },
        {
        title: "Foster inclusion",
        description: `<p><b>Recognizing the value that different perspectives and cultures bring to an
        organization.</b></p>
    <ul>
    <li>Seeks to understand different perspectives and cultures.</li>
    <li>Contributes to a work climate where differences are valued and
        supported.
    </li>
    <li>Applies others’ diverse experiences, styles, backgrounds, and
        perspectives
        to get results.</li>
    <li>Is sensitive to cultural norms, expectations, and ways of communicating.
    </li>
    </ul>`,
        showme: false,
        color: "lgreen"
        },
        {
        title: "Cultivate innovation",
        description: `<p><b>Creating new and better ways for the organization to be successful.</b>
        </p>
        <ul>
            <li>Comes up with useful ideas that are new, better, or unique.</li>
            <li>Introduces new ways of looking at problems.</li>
            <li>Can take a creative idea and put it into practice.</li>
            <li>Encourages diverse thinking to promote and nurture innovation.</li>
        </ul>`,
        showme: false,
        color: "blue"
        },
        {
        title: "Demonstrate agility",
        description: `<p><b>Adapting approach and demeaner in real time to match the shifting demands
        of
        different situations.</b></p>
    <ul>
    <li>Picks up on situational cues and adjusts in the moment.</li>
    <li>Readily adapts personal, interpersonal, and leadership behavior.</li>
    <li>Understands that different situations may call for different approaches.
    </li>
    <li>Can act differently depending on the circumstances.</li>
    </ul>`,
        showme: false,
        color: "yellow"
        },
        {
        title: "Drive results",
        description: `<p><b>Consistently achieving results, even under tough circumstances.</b></p>
        <ul>
            <li>Has a strong bottom-line orientation.</li>
            <li>Persists in accomplishing objectives despite obstacles and setbacks.
            </li>
            <li>Has a track record of exceeding goals successfully.</li>
            <li>Pushes self and helps others achieve results.</li>
        </ul>`,
        showme: false,
        color: "lgreen1"
        },
        {
        title: "Work together",
        description: `<p><b>Building partnerships and working collaboratively with others to meet
        shared
        objectives.</b></p>
    <ul>
    <li>Works cooperatively with others across the organization to achieve
        shared
        objectives.</li>
    <li>Represents own interests while being fair to others and their areas.
    </li>
    <li>Partners with others to get work done.</li>
    <li>Credits others for their contributions and accomplishments.</li>
    <li>Gains trust and support of others.</li>
    </ul>`,
        showme: false,
        color: "green"
        }
    ]

## HTML
    <div class="d-flex flex-wrap gap-3">
        <div class="hexa shadow" [ngClass]="{'active  bg-white':showme[i]}"
            *ngFor="let item of tiles; let i = index;">
            <button class="ripple hex-title {{item.color}}" (click)="toggle(i)">
                <div class="num">0{{i+1}}</div>
                {{item.title}}
            </button>
            <div class="desc " [ngClass]="{'active': showme[i]}" [innerHTML]="item.description">
            </div>
        </div>
    </div>

## SCSS
    .hexa {
        width: 32%;
        text-align: left;
        border-radius: 20px 0 20px 0;
        overflow: hidden;
        height: 120px;
        transition: height 0.5s ease;
        position: relative;
        .num {
            font-size: 106px;
            opacity: 0.1;
            position: absolute;
            right: -2px;
            top: -3px;
            font-family: fantasy;
        }

        &.active {
            height: 470px;
        }
        .hex-title {
            font-size: 28px;
            color: #fff;
            padding: 10px;
            text-align: center;
            /* background-color: #279989; */
            border-radius: 20px 0 20px 0;
            min-height: 120px;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            width: 100%;
            position: relative;
            z-index: 2;
        }
        .desc {
            padding: 10px;
            box-shadow: 0 0 2px #ccc3;
            position: relative;
            z-index: 1;
            transform: translateY(-100%);
            transition: all 0.5s ease;

            &.active {
            transform: translateY(0);
            }
        }
        }