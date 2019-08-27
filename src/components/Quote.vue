<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot></slot><!-- slot je jer ce quote content tj sadrzaj doci iz spolja. sa <slot> samo kreiramo mesto gde cemo renderovati, tzv holder u koji cemo da stavimo QuoteGrid...valjda -->
                
            </div>
        </div>
    </div>
</template>

<script></script>

<style>
    .panel-body {
        font-family: 'Arizonia', cursive;
        font-size: 24px;
        color: #6e6e6e;
    }

    .quote {
        cursor: pointer;
    }

    .quote:hover {
        background-color: orangered;
        color: #fff;
    }
</style>