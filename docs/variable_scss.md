## CSS to remove labels
Create file call _variable.scss and paste the below code.

    $blue: #005f86;
    $lblue: #279989;
    $mblue: #007582;
    $red: #9e2a2f;
    $lgreen: #a9ad36;
    $green: #658d1b;

    $light-gray: #ccc;
    $light-blue: #e6eff3;

    $primary: $blue;
    $secondary: $lblue;
    $tertiary: $mblue;
    $white: #fff;
    $shadow: #868686;
    $selected_shadow: #002d44;
    $radius: 5px;

    $dvm_width: 394px;
    $dvm_height: 671px;

    // Small tablets and large smartphones (landscape view)
    $screen-sm-min: 576px;

    // Small tablets (portrait view)
    $screen-md-min: 768px;

    // Tablets and small desktops
    $screen-lg-min: 1100px;

    // Large tablets and desktops
    $screen-xl-min: 1200px;

    // Small devices
    @mixin sm {
    @media (max-width: #{$screen-sm-min}) {
        @content;
    }
    }

    // Medium devices
    @mixin md {
    @media (max-width: #{$screen-md-min}) {
        @content;
    }
    }

    // Large devices
    @mixin lg {
    @media (max-width: #{$screen-lg-min}) {
        @content;
    }
    }

    // Extra large devices
    @mixin xl {
    @media (max-width: #{$screen-xl-min}) {
        @content;
    }
    }

    // Custom width
    @mixin min($width) {
    @media (max-width: #{$width}) {
        @content;
    }
    }
