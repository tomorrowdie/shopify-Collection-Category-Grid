{% comment %}
  Collection Category Grid v2.5
  Added: Optional section heading with enable/disable toggle
  
  New Features:
  - Section heading (optional)
  - Subtext/description (optional)
  - Heading size options (Small, Medium, Large)
  - Text alignment (Left, Center, Right)
  - Easy enable/disable toggle
{% endcomment %}

<style>
  /* Section Heading Styles */
  .collection-grid-header {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 20px 40px;
  }

  .collection-grid-header.align-left {
    text-align: left;
  }

  .collection-grid-header.align-center {
    text-align: center;
  }

  .collection-grid-header.align-right {
    text-align: right;
  }

  .collection-grid-header h2.size-small {
    font-size: 28px;
    margin: 0 0 10px 0;
  }

  .collection-grid-header h2.size-medium {
    font-size: 36px;
    margin: 0 0 12px 0;
  }

  .collection-grid-header h2.size-large {
    font-size: 48px;
    margin: 0 0 15px 0;
  }

  .collection-grid-header h2 {
    font-weight: 700;
    line-height: 1.2;
    color: #000;
  }

  .collection-grid-header p {
    font-size: 18px;
    color: #666;
    margin: 0;
    line-height: 1.5;
    max-width: 800px;
  }

  .collection-grid-header.align-center p {
    margin-left: auto;
    margin-right: auto;
  }

  .collection-grid-header.align-right p {
    margin-left: auto;
  }

  /* Collection Grid Styles */
  .collection-category-grid {
    padding: {{ section.settings.top_padding }}px 0 {{ section.settings.bottom_padding }}px;
  }

  .collection-grid-container {
    display: grid;
    grid-template-columns: repeat({{ section.settings.columns_desktop }}, 1fr);
    gap: 20px;
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 20px;
  }

  .collection-category-item {
    position: relative;
    overflow: hidden;
    border-radius: 8px;
    aspect-ratio: 4/5;
    text-decoration: none;
    display: block;
  }

  .collection-category-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
  }

  .collection-category-item:hover img {
    transform: scale(1.05);
  }

  .collection-category-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    background: linear-gradient(to top, rgba(0,0,0,0.8), transparent);
    padding: 30px 20px 20px;
    color: white;
  }

  .collection-category-title {
    font-size: 20px;
    font-weight: 600;
    margin: 0;
    text-align: center;
    text-decoration: none;
  }

  /* Mobile Styles */
  @media (max-width: 768px) {
    .collection-grid-header h2.size-small {
      font-size: 24px;
    }

    .collection-grid-header h2.size-medium {
      font-size: 28px;
    }

    .collection-grid-header h2.size-large {
      font-size: 36px;
    }

    .collection-grid-header p {
      font-size: 16px;
    }

    {% if section.settings.mobile_layout == 'scroll' %}
      .collection-grid-container {
        display: flex;
        grid-template-columns: none;
        gap: 15px;
        overflow-x: auto;
        scroll-snap-type: x mandatory;
        -webkit-overflow-scrolling: touch;
        padding: 0 20px;
        max-width: 100%;
      }

      .collection-grid-container::-webkit-scrollbar {
        height: 8px;
      }

      .collection-grid-container::-webkit-scrollbar-track {
        background: #f1f1f1;
        border-radius: 10px;
      }

      .collection-grid-container::-webkit-scrollbar-thumb {
        background: #888;
        border-radius: 10px;
      }

      .collection-grid-container::-webkit-scrollbar-thumb:hover {
        background: #555;
      }

      .collection-category-item {
        min-width: 280px;
        flex-shrink: 0;
        scroll-snap-align: start;
      }
    {% else %}
      .collection-grid-container {
        grid-template-columns: repeat(2, 1fr);
        gap: 15px;
      }
    {% endif %}
  }
</style>

{% if section.settings.show_heading %}
<div class="collection-grid-header align-{{ section.settings.heading_alignment }}">
  {% if section.settings.heading_text != blank %}
    <h2 class="size-{{ section.settings.heading_size }}">{{ section.settings.heading_text }}</h2>
  {% endif %}
  {% if section.settings.subtext != blank %}
    <p>{{ section.settings.subtext }}</p>
  {% endif %}
</div>
{% endif %}

<div class="collection-category-grid">
  <div class="collection-grid-container">
    
    {% for i in (1..6) %}
      {% case i %}
        {% when 1 %}
          {% assign image = section.settings.category_1_image %}
          {% assign heading = section.settings.category_1_heading %}
          {% assign link = section.settings.category_1_link %}
        {% when 2 %}
          {% assign image = section.settings.category_2_image %}
          {% assign heading = section.settings.category_2_heading %}
          {% assign link = section.settings.category_2_link %}
        {% when 3 %}
          {% assign image = section.settings.category_3_image %}
          {% assign heading = section.settings.category_3_heading %}
          {% assign link = section.settings.category_3_link %}
        {% when 4 %}
          {% assign image = section.settings.category_4_image %}
          {% assign heading = section.settings.category_4_heading %}
          {% assign link = section.settings.category_4_link %}
        {% when 5 %}
          {% assign image = section.settings.category_5_image %}
          {% assign heading = section.settings.category_5_heading %}
          {% assign link = section.settings.category_5_link %}
        {% when 6 %}
          {% assign image = section.settings.category_6_image %}
          {% assign heading = section.settings.category_6_heading %}
          {% assign link = section.settings.category_6_link %}
      {% endcase %}
      
      {% if image != blank %}
        <a href="{{ link }}" class="collection-category-item">
          <img 
            src="{{ image | image_url: width: 600 }}" 
            alt="{{ heading | default: 'Collection' }}"
            loading="lazy"
          >
          {% if heading != blank %}
            <div class="collection-category-overlay">
              <h3 class="collection-category-title">{{ heading }}</h3>
            </div>
          {% endif %}
        </a>
      {% endif %}
    {% endfor %}
    
  </div>
</div>

{% schema %}
{
  "name": "Collection Category Grid",
  "tag": "section",
  "class": "collection-grid-section",
  "settings": [
    {
      "type": "header",
      "content": "Section Heading"
    },
    {
      "type": "checkbox",
      "id": "show_heading",
      "label": "Show section heading",
      "default": false,
      "info": "Display an optional heading above the collection grid"
    },
    {
      "type": "text",
      "id": "heading_text",
      "label": "Heading",
      "default": "Shop by Collection",
      "info": "Main heading text"
    },
    {
      "type": "textarea",
      "id": "subtext",
      "label": "Subtext",
      "default": "Discover our curated collections",
      "info": "Optional description below heading"
    },
    {
      "type": "select",
      "id": "heading_size",
      "label": "Heading size",
      "options": [
        {
          "value": "small",
          "label": "Small"
        },
        {
          "value": "medium",
          "label": "Medium"
        },
        {
          "value": "large",
          "label": "Large"
        }
      ],
      "default": "medium"
    },
    {
      "type": "select",
      "id": "heading_alignment",
      "label": "Text alignment",
      "options": [
        {
          "value": "left",
          "label": "Left"
        },
        {
          "value": "center",
          "label": "Center"
        },
        {
          "value": "right",
          "label": "Right"
        }
      ],
      "default": "center"
    },
    {
      "type": "header",
      "content": "Layout Settings"
    },
    {
      "type": "range",
      "id": "columns_desktop",
      "min": 2,
      "max": 6,
      "step": 1,
      "label": "Number of columns on desktop",
      "default": 6
    },
    {
      "type": "select",
      "id": "mobile_layout",
      "label": "Mobile Layout",
      "options": [
        {
          "value": "grid",
          "label": "Grid (2 columns)"
        },
        {
          "value": "scroll",
          "label": "Horizontal Scroll"
        }
      ],
      "default": "scroll",
      "info": "Choose how categories display on mobile devices"
    },
    {
      "type": "header",
      "content": "Section Padding"
    },
    {
      "type": "range",
      "id": "top_padding",
      "min": 0,
      "max": 100,
      "step": 4,
      "unit": "px",
      "label": "Top padding",
      "default": 36
    },
    {
      "type": "range",
      "id": "bottom_padding",
      "min": 0,
      "max": 100,
      "step": 4,
      "unit": "px",
      "label": "Bottom padding",
      "default": 36
    },
    {
      "type": "header",
      "content": "Category 1"
    },
    {
      "type": "image_picker",
      "id": "category_1_image",
      "label": "Image"
    },
    {
      "type": "text",
      "id": "category_1_heading",
      "label": "Heading",
      "default": "Category 1"
    },
    {
      "type": "url",
      "id": "category_1_link",
      "label": "Link"
    },
    {
      "type": "header",
      "content": "Category 2"
    },
    {
      "type": "image_picker",
      "id": "category_2_image",
      "label": "Image"
    },
    {
      "type": "text",
      "id": "category_2_heading",
      "label": "Heading",
      "default": "Category 2"
    },
    {
      "type": "url",
      "id": "category_2_link",
      "label": "Link"
    },
    {
      "type": "header",
      "content": "Category 3"
    },
    {
      "type": "image_picker",
      "id": "category_3_image",
      "label": "Image"
    },
    {
      "type": "text",
      "id": "category_3_heading",
      "label": "Heading",
      "default": "Category 3"
    },
    {
      "type": "url",
      "id": "category_3_link",
      "label": "Link"
    },
    {
      "type": "header",
      "content": "Category 4"
    },
    {
      "type": "image_picker",
      "id": "category_4_image",
      "label": "Image"
    },
    {
      "type": "text",
      "id": "category_4_heading",
      "label": "Heading",
      "default": "Category 4"
    },
    {
      "type": "url",
      "id": "category_4_link",
      "label": "Link"
    },
    {
      "type": "header",
      "content": "Category 5"
    },
    {
      "type": "image_picker",
      "id": "category_5_image",
      "label": "Image"
    },
    {
      "type": "text",
      "id": "category_5_heading",
      "label": "Heading",
      "default": "Category 5"
    },
    {
      "type": "url",
      "id": "category_5_link",
      "label": "Link"
    },
    {
      "type": "header",
      "content": "Category 6"
    },
    {
      "type": "image_picker",
      "id": "category_6_image",
      "label": "Image"
    },
    {
      "type": "text",
      "id": "category_6_heading",
      "label": "Heading",
      "default": "Category 6"
    },
    {
      "type": "url",
      "id": "category_6_link",
      "label": "Link"
    }
  ],
  "presets": [
    {
      "name": "Collection Category Grid",
      "category": "Collection"
    }
  ]
}
{% endschema %}
