# NativeScript Range Seek Bar

A NativeScript Range Seek Bar widget.

### Based on

[TTRangeSlider ](https://github.com/TomThorpe/TTRangeSlider) for iOS

[Crystal Range Seekbar](https://github.com/syedowaisali/crystal-range-seekbar) for Android

## Installation

Run `tns plugin add nativescript-range-seek-bar`

## API

### Events

- **rangeSeekBarChanged**  
  Triggered when user has changed minimum value or maximum value on the Range Seek Bar.
- **rangeSeekBarFinalValue**  
  Triggered when user has finished touch on the Range Seek Bar.

### Instance Properties

- **minValue** - _Number_  
  Gets or sets minimum value of the Range Seek Bar.
- **maxValue** - _Number_  
  Gets or sets maximum value of the Range Seek Bar.
- **minStartValue** - _Number_  
  Gets or sets minimum start value of the Range Seek Bar.
- **maxStartValue** - _Number_  
  Gets or sets maximum start value of the Range Seek Bar.
- **minRange** - _Number_  
  Gets or sets minimum range of two thumb.
- **step** - _Number_  
  Gets or sets minimum steps between range, default is 1.
- **cornerRadius** - _Number_  
  Gets or sets corner radius of two thumb.
- **barHeight** - _Number_  
  Gets or sets bar height of the Range Seek Bar.
- **barColor** - _Color_  
  Gets or sets bar color of the Range Seek Bar.
- **barHighlightColor** - _Color_  
  Gets or sets bar highlight color of the Range Seek Bar.
- **thumbColor** - _Color_  
  Gets or sets color of two thumb.

## Usage in Angular

- Import `NativeScriptUIRangeSeekBarModule` in `NgModule`:

```typescript
import { NativeScriptUIRangeSeekBarModule } from "nativescript-range-seek-bar/angular";
//......
@NgModule({
	//......
	imports: [
        //......
		NativeScriptUIRangeSeekBarModule,
        //......
	],
    //......
})
```

```html
<!-- app.component.html -->
<StackLayout>
	<RangeSeekBar
		[minValue]="rangeSeekBarProp.minValue"
		[maxValue]="rangeSeekBarProp.maxValue"
		[minStartValue]="rangeSeekBarProp.minStartValue"
		[maxStartValue]="rangeSeekBarProp.maxStartValue"
		[minRange]="rangeSeekBarProp.minRange"
		[step]="rangeSeekBarProp.step"
		(rangeSeekBarChanged)="rangeSeekBarChanged($event)"
		(rangeSeekBarFinalValue)="rangeSeekBarFinalValue($event)"
		class="range-seek-bar"
	></RangeSeekBar>
</StackLayout>
```

```css
/*app.css*/
.range-seek-bar {
	bar-color: #8990c4;
	bar-highlight-color: #2434ad;
	thumb-color: #1a246d;
	bar-height: 10;
	corner-radius: 30;
}
```

```ts
// app.component.ts
import { Component } from "@angular/core";
import { RangeSeekBarEventData } from "nativescript-range-seek-bar";

@Component({
	selector: "ns-app",
	templateUrl: "app.component.html",
})
export class AppComponent {
	public rangeSeekBarProp = {
		minValue: 0,
		maxValue: 100,
		minStartValue: 0,
		maxStartValue: 100,
		minRange: 0,
		step: 1,
	};

	constructor() {}

	rangeSeekBarChanged(event: RangeSeekBarEventData) {
		console.log("rangeSeekBarChanged: ", event.value);
	}

	rangeSeekBarFinalValue(event: RangeSeekBarEventData) {
		console.log("rangeSeekBarFinalValue: ", event.value);
	}
}
```

# To publish updates:

1. Commit your changes and push to the repository.
2. `cd src`
3. `npm run publish`
